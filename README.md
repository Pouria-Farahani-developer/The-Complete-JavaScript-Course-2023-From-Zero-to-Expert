# javascript-jonas
<div dir="rtl">
 نکته : در واقع دستور chain یا همان ؟ می آید مثل and برای  ما عمل میکند و هر جایی که مقدار undefined باشد همان مقدار را برای  ما برمیگرداند و در واقع نمی گذارد  چنین دستوری اجرا شود .
<pre dir='ltr'>
  console.log(name?.family.city)
  //output undefined?.family.city
</pre>
 نکته : در واقع در مثال بالا برای ما همان undefined را بر میگرداند . نمی گذارد که ادامه زنجیره هم برای ما اجرا شود .
  
 اما اگر در مثال بالا از همان chainاستفاده نکنیم ، باعث می شود که به ما خطا برگرداند .
  
 نکته : ما می توانیم بیاییم و multiple chain داشته باشیم .

 نحوه حلقه زدن روی  آرایه به وسیله  for :‌
<pre dir='ltr'>
const days = ['sat','sun','mon','tue','wed','thu'];
    for(const day of  days){
      consol.log(day) //output 'sat','sun',...
    }
</pre>

 یادآوری : یک نحوه صداکردن عضوهای آرایه بدین شکل می باشد.  
 <pre dir='ltr'>
    const storage = restaurant.openingHours[day];
 </pre>
 <pre dir='ltr'>
    const storage = restaurant.openingHours[day]?.open ?? 'closed';
 </pre>
روشی برای چک کردن اینکه متدی که میخواهیم در داخل آبجکت وجود دارد و اگر وجود داشت برای ما اجرا شود :
<pre dir='ltr'>
    conso.log(restaurant.order?.(0,1) ?? 'Method does not exit');
 </pre>

 مقایسه دو روش برای اینکه ببینیم که کدام روش بهینه تر است . 
  <pre dir='ltr'>
    const user = ['array'];
    console.log(users[0]?.name ?? 'Users array empty');
  </pre>

  OR

  <pre dir='ltr'>
    const user = ['array'];
    if(user.length > 0) console.log(users[0].name);
    else console.log('user array empty');
  </pre>
 نتیجه گیری : پس می توانیم نتیجه گیری کنیم که مورد اول بسیار خلاصه تر و منطقی تر است . 
  
 نکته : حلقه زدن روی آبجکت ها  
    <pre dir='ltr'>
      for(const day of object.key(openingHours)){
        console.log(day)
      }
    </pre>
  
 نکته : در واقع بایستی به این نکته اشاره کنیم که کد object.key می آید و برای ما خروجی یک آرایه را میدهد .
    <pre dir='ltr'>
      const properties = Object.keys(openingHours);
      console.log(properties);
    </pre>
    <pre dir='ltr'>
      const Values = object.values(openingHours);
      console.log(Values)
    </pre>
مبحث مجموعه ها : 
    <pre dir='ltr'>
      const orderSet = new Set(['ali','pouria','arman','pouria','arman']);
      console.log(orderSet) //output {'ali','pouria','arman'}
    </pre>
 در واقع مجموعه ها عضو های تکراری یک آرایه را به شمار نمی آورد .\
 از آنجایی که آرایه ها قابل  تکرار هستند ، پس در نتیجه میتوانیم برای آن  ها هم set را در نظر بگیریم .\
    <pre dir='ltr'>
      console.log(new Set('Jonas'));
      console.log(orderSet.size) //output:3
    </pre>
 همچنین ما میتوانیم بیاییم با استفاده از متد has چک کنیم که آیا آرایه مقدار دلخواه ما را شامل می شود یا خیر .\
    <pre dir='ltr'>
      console.log(orderSet.has('ali)) //output:true
    </pre>
 همچنین ما میتوانیم بیاییم از متد add برای اضافه کردن مقدار به مجموعه ها استفاده کنیم .
    <pre dir='ltr'>
      orderset.add('hamidreza')
    </pre>
نحوه حذف کردن یک عنصر از داخل set :
    <pre dir='ltr'>
      orderSet.delete('ali)
    </pre>
 نکته:از set بیشتر به حالتی استفاده میشود که چک بکنند آیا مقداری داخل sets وجود دارد یا خیر ، در واقع نمی آیند مقداری از داخل مجموعه ها به صورت آرایه ای بیرون بکشند.برای این حالتی که مد نظر ما هست باید از آرایه ها استفاده کنید.
 
 ما میتوانیم بیاییم با استفاده از دستور clear تمامی مقادیر که داخل sets وجود دارد را پاک کنیم .
    <pre dir='ltr'>
      orderSet.clear() //output:{}
    </pre>
 همچنین ما میتوانیم بیاییم و روی sets حلقه بزنیم . مثال :
    <pre dir='ltr'>
      for(const order of orderSet) console.log(order)
    </pre>
نکته: در واقع استفاده اصلی از مجموعه ها برای این است که مقادیر یونیک داشته باشیم .

 مثال:
    <pre dir='ltr'>
      const staff = ['waiter','chef','waiter',manager',Chef','Waiter'];
      const staffUnique = new set(staff);
      console.log(staffUnique);
    </pre>
 روش تبدیل یک set به یک آرایه :
    <pre dir='ltr'>
      const staff = ['waiter','chef','waiter',manager',Chef','Waiter'];
      const staffUnique = [...new set(staff)];
      console.log(staffUnique);
    </pre>
 نکته:اگر بخواهیم بدونیم که در یک کلمه چند تا حرف مختلف وجود دارد میتوانیم از set استفاده کنیم .
    <pre dir='ltr'>
      console.log(new set('jonasschmedtmann').size);
    </pre>
نکته: اگر ترتیب آرایه ها برای ما اهمیت بیشتری نسبت به unique بودن مقادیر برامون داره میتوانیم از آرایه ها استفاده کنیم . ولی اگر unique بودن مقادیر اهمیت بیشتری نسبت به ترتیب مقادیر برامون داره بایستی از set استفاده کنیم .

 مبحث نقشه ها:
 
تفاوت بزرگ بین MAP و OBJECT ها در این است که  در MAP کلید ها میتوانند هر مقدار را داشته باشند ، اما در object ها کلید ها فقط می توانند رشته باشند .
  <pre dir='ltr'>
    const rest = new Map();
    rest.set('name','pouria') // اولین مورد مربوط به مقدار کلید و دومین مورد مربوط به مقدار اختصاص داده شده به کلید می باشد
    rest.set(1,'firenze')
    rest.set(2,'Lisbon')
  </pre>
 نکته : هنگامی که یکی از دستورهای rest.set را هم log بگیریم نه تنها map ما را اپدیت نمیکند بلکه map کلی را هم برای ما برمیگرداند که این باعث می شود با لاگ گرفتن هر یک از دستورات به کل map هم دسترسی داشته باشیم .
 
 ما حتی میتوانیم بیایم به صورت chaining تمامی map خود را اپدیت کنیم.
  <pre dir='ltr'>
    rest.set('catgories',['italian','pizzeria']).set('open',11).set('close',13)
  </pre>
 در واقع ساز و کار مثال بالا ، به چه شکل است ، بدین شکل می شود که چون با هر بار set کردن map ما بروز می شود و به ما برگردانده میشود پس در نتیجه ما تمامی این مراحل انگار داریم به صورت تک به تک انجام میدهیم .
 
 همچنین ما در map ، می توانیم به وسیله استفاده از متد get به مقادیر داخل map دسترسی داشته باشیم .

<pre dir='ltr'>
  console.log(rest.get('name));
  console.log(rest.get(2));
</pre>
ما میتوانیم در map با متد has چک کنیم که آیا کلید مدنظر ما در map وجود دارد یا خیر . مثال :
<pre dir='ltr'>
  rest.has('categories');
</pre>
همچنین ما میتوانیم بیاییم به وسیله متد delete و با استفاده از key ها موجود در map ، عناصری که نمیخواهیم را حذف کنیم .
<pre dir='ltr'>
  rest.delete(2);
</pre>
نکته : در map ها هم همانند set ما از متدی به نام size می توانیم استفاده کنیم . همچنین به مانند set متدی دیگری به نام clear وجود دارد که میتوانیم تمام عضوها داخل map را پاک کنیم .

<pre dir='ltr'>
 console.log(rest.size);
 rest.clear();
</pre>
نکته : Map و set همگی در es6 معرفی شده اند .
نکته : از آنجایی که ما گفتیم در map میتوانیم از هر عنصری به عنوان کلید استفاده کنیم پس در اینجا میخواهیم مثالی بزنیم که در آن از آرایه به عنوان کلید استفاده شود . 
<pre dir='ltr'>
  rest.set([1,2],'Test');
</pre>
همچنین ما میتوانیم از المان ها به عنوان کلید Map خود استفاده کنیم . 

<pre dir='ltr'>
  rest.set(document.querySelector('h1),'Heading');
</pre>
مثال:
<pre dir='ltr'>
 const question = new Map([
  ['qustion','what is the best programming language in the world?'],
  [1,'c'],
  [2,'java'],
  [3,'javascript']
 ])
 console.log(question);
</pre>
ساختاری که در داخل Map برای question وجود دارد دقیقا مانند ساختار مثال زیر می باشد . 
<pre dir='ltr'>
  console.log(Object.entries(openingHours));
</pre>
نکته: این متد فقط هنگامی جواب میدهد که ما یک نمونه سازی از Map کرده باشیم .
نحوه حلقه زدن روی Map :
<pre dir='ltr'>
 for(const [key,value] of question){
  if(typeof key === 'number') console.log(`Answer ${key}:${value}`)
 }
</pre>
نکته: در حالت کلی باید توجه داشته باشیم که برای حلقه زدن بر روی object و یا Map ابتدا بایستی از متد entries استفاده کنیم ولی در مثال فوق چون ما خودمون از قبل entries کرده بودیم مقادیر خودمون را پس لازم به اینکار نبود.
<pre dir='ltr'>
 //convert Map to array
 console.log([...question])
 //other example
 console.log(question.keys());
 console.log(question.values());
</pre>
سوال : از کدام ساختار داده استفاده کنیم ؟
Source OF Data : 
1) From the program itself : Data written directly in source code.
2) From the UI : Data input from the user or data written in Dom
3) From external sources : Data Fetched for example from web Api(Application Programming Interface)
   
نکته : اگر احتیاج داشتیم که یک Simple list داشته باشیم بهترین انتخاب استفاده از Array or Sets ولی اگر احتیاج به Key/Value PAIRS داشتیم بهترین انتخاب استفاده از Object or Maps می باشد .  در واقع میتوان گفت : keys allow us to describe values .

بقیه ساختار داده هایی که وجود دارند :
other built-in: ساختار داده هایی که در جاوا اسکریپ موجود است
weakMap
weakSet
Non-Built in :ساختار داده هایی که در جاوا اسکریپ موجود نمی باشد 
stacks - queues - linked lists - trees - hash tables
چه زمانهایی از هر یک از ساختار داده ها استفاده کنیم :

Arrays :

use when you need ordered list of values (might contain duplicate)

use when you need to manipulate data

sets :

use when you need to work with unique values

use when high-performance is really important

use to remove duplicates from arrays

Objects:

More Traditional key/value store ("abused" objects)

easier to write and access values with . and []

use when need to include functions (methods)

use when working with json (can convert to map)

maps :

better performance

keys can have any data type

easy to iterate

easy to compute size

use when you simply need to map key to values

use when you need keys that are not strings
مبحث کار با رشته ها :

ما میتوانیم همانند آرایه ها با رشته ها رفتار کنیم . به طور مثال : 
<pre dir='ltr'>
 const airline = 'TAP AIR Portugal';
 const plane = 'A320';
 console.log(plane[0]); //output : A
 console.log('B737'[0]);
 console.log(airline.length) ;
 console.log('B737'.length);
 console.log(airline.indexof('r')); //output : 6
 console.log(airline.lastIndexOf('r')); //output : 10
 console.log(airline.indexOf('Portugal')); //this method is case sensitive
</pre>
معرفی متد slice : 
<pre dir='ltr'>
 console.log(airline.slice(4)) //Air Portugal
 console.log(airline.slice(4,7)) //Air
</pre>
نکته : بایستی این نکته را بدانیم که اگر خواستیم از رشته فوق استفاده کنیم ابتدا بایستی آن را در یک متغیر ذخیره کنیم و متد slice رشته اصلی ما را تغییر نمیدهد. 

مثال : در این مثال میخواهیم اولین کلمه و اخرین کلمه مقدار متغیر airline را جدا کنیم .
<pre dir='ltr'>
 console.log(airline.slice(0,airline.indexOf(' ')));
 console.log(airline.lastIndexOf+1); // we plus with 1 because we have not extra space
</pre>
<pre dir='ltr'>
 console.log(airline.slice(-2)) // در این روش رشته را از آخر شروع به شمارش می کند
 console.log(airline.slice(1,-1)) // این دوتا عدد باعث می شود که یک کلمه از ابتدا و یک کلمه از انتها برداشته شود و در نهایت باقی کلمات نمایش داده شود 
</pre>
قسمت کار با رشته ها - بخش 2 :
<pre dir='ltr'>
 const airline = 'TAP AIR Portugal';
 console.log(airline.toLowerCase());
 console.log(airline.toUpperCase());
 console.log('Jonas'.toLowerCase());
</pre>
<pre dir='ltr'>
 //Fix Capitalization in name
 const passenger = 'jOnAs';
 const passengerLower = passenger.toLowerCase();
 const passengerCorrect = passengerLower[0].toUpperCase() + passengerLower.slice(1);
 console.log(passengerCorrect);
</pre>
<pre dir='ltr'>
 const email = 'hello@jonas.io';
 const loginEmail=' Hello@Jonas.Io \n';
 const normalizedEmail=loginEmail.toLowerCase().trim();
 console.log(email === normalizedEmail);
</pre>
توضیحاتی در مورد replacing : 
<pre dir='ltr'>
 const priceGB = '288,971';
 const priceUS = priceGB.replace('1','8').replace(',','.');
 console.log(priceUS);
</pre>
<pre dir='ltr'>
 const announcement = 'All passengers come to boarding door 23. Boarding door 23!';
 console.log(announcement.replace('door','gate')); // در این مثال فقط کلمه اول که پیدا شود جایگزین می شود و سایر کلمات جایگزین نمی شود 
 console.log(announcement.replace(/door/g,'gate')); // اما در این مثال تمام کلماتی که مد نظر ما در جمله هست جایگزین می شود
</pre>
نکته : در مثال فوق ، دومین مثال حکم regular expression پیدا کرد و با استفاده از کلمه g چون به معنی global می شود ، در نتیجه تمامی کلمات جایگزین می شوند . در این روش کوچک و یا بزرگ بودن کلمات هم دارای اهمیت می باشند .

توضیح دادن متد هایی که برای ما حالت Boolean دارند :
<pre dir='ltr'>
 const plane = 'A320neo';
 console.log(plane.includes('A320'));
 console.log(plane.startsWith('Air'));
 console.log(plane.endsWith('neo'));
</pre>
برای مقایسه کردن string ها ، اولین و بهترین کار در این است که ابتدا ما بیاییم و رشته های خود را به lowercase تبدیل کنیم و سپس عملیات مقایسه را روی آن ها انجام بدهیم.
کار با رشته ها ( قسمت سوم ) : 
کار با split ها : 
<pre dir='ltr'>
 console.log('a+Bery+nice+string'.split('+')); //output:['a','very','nice','string']);
 console.log('Jonas Schmedtmann'.split(' '));
 const [firstName,lastName]='Jonas Schmedtmann'.split(' ');
</pre>
مثالی برای استفاده از متد join : 
<pre dir='ltr'>
 const newName = ['Mr.',firstName,lastName.toUpperCase()].join(' ')
 console.log(newName) //output Mr. Jonas schmedtmann
</pre>
مثال : 
<pre dir='ltr'>
 const capitalizeName = function (name) {
  const names = name.split(' ');
  const namesUpper = [];

  for(const n of names){
   namesUpper.push(n[0].toUpperCase() + n.slice(1));
  }

  console.log(namesUpper.joini(' '));
 }

 capitalizeName('jessica ann smith davis');
 capitalizeName('jonas schmedtmann');
</pre>
راه حل دوم :
<pre dir='ltr'>
 const capitalizeName = function (name) {
  const names = name.split(' ');
  const namesUpper = [];

  for(const n of names){
   namesUpper.push(n.replace(n[0],n[0].toUpperCase()));
  }

  console.log(namesUpper.joini(' '));
 }

 capitalizeName('jessica ann smith davis');
 capitalizeName('jonas schmedtmann');
</pre>
توضیح در مورد padding ها : 
<pre dir='ltr'>
 const message = 'Go to gate 23!';
 console.log(message.padStart(25,'+')); // در واقع متغیر اول مقداری هست که میخواهیم طول رشته به همان اندازه باشد و متغیر دوم المانی هست که میخواهیم باقی رشته با آن پر شود
</pre>
<pre dir='ltr'>
 const message = 'Go to gate 25!';
 console.log(message.padEnd(35,'-'));
</pre>
در واقع یک نمونه مثال برای استفاده از padding ها ، همان شماره کارت های اعتباری می باشد که با * نمایش می دهیم .

نکته : ما بایستی به این نکته توجه داشته باشیم که pad برای رشته های str کاربرد دارد.

یک مثال دیگر از استفاده padStart : 
<pre dir='ltr'>
 const maskCreditCard = function (number){
  const str = number + '';
  const last = str.slice(-4);
  return last.padStart(str.length,'*');
 }

 console.log(maskCreditCard(64637836));
 console.log(maskCreditCard(43378463864647384));
</pre>
همین روالی که توضیح داده شد را میتوانیم برای padEnd هم مورد استفاده قرار بدهیم .

توضیح دادن متد Repeat : 
<pre dir='ltr'>
  const message2 = 'Bad waether... All Departues Delayed ...';
  console.log(message2.repeat(5));
</pre>



































 
    
    
    
    
    
    
    
    
    
    
    
    
     
     
    
    
    
    
    
  
    
    
    
    

    

  
    
</div>
