# javascript-jonas
<div dir="rtl" style={code:dir:ltr}>
  نکته : در واقع دستور chain یا همان ؟ می آید مثل and برای  ما عمل میکند و هر جایی که مقدار undefined باشد همان مقدار را برای  ما برمیگرداند و در واقع نمی گذارد  چنین دستوری اجرا شود .
```
  console.log(name?.family.city)
  //output undefined?.family.city
```


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
    نحوه حذف کردن یک عنصر از داخل set :\
    <pre dir='ltr'>
      orderSet.delete('ali)
    </pre>
    نکته:از set بیشتر به حالتی استفاده میشود که چک بکنند آیا مقداری داخل sets وجود دارد یا خیر ، در واقع نمی آیند مقداری از داخل مجموعه ها به صورت آرایه ای بیرون بکشند.برای این حالتی      که مد نظر ما هست باید از آرایه ها استفاده کنید.\
    ما میتوانیم بیاییم با استفاده از دستور clear تمامی مقادیر که داخل sets وجود دارد را پاک کنیم .\
    <pre dir='ltr'>
      orderSet.clear() //output:{}
    </pre>
    همچنین ما میتوانیم بیاییم و روی sets حلقه بزنیم . مثال :
    <pre dir='ltr'>
      for(const order of orderSet) console.log(order)
    </pre>
    نکته: در واقع استفاده اصلی از مجموعه ها برای این است که مقادیر یونیک داشته باشیم .\
    مثال:\
    <pre dir='ltr'>
      const staff = ['waiter','chef','waiter',manager',Chef','Waiter'];
      const staffUnique = new set(staff);
      console.log(staffUnique);
    </pre>
    روش تبدیل یک set به یک آرایه :\
    <pre dir='ltr'>
      const staff = ['waiter','chef','waiter',manager',Chef','Waiter'];
      const staffUnique = [...new set(staff)];
      console.log(staffUnique);
    </pre>
    نکته:اگر بخواهیم بدونیم که در یک کلمه چند تا حرف مختلف وجود دارد میتوانیم از set استفاده کنیم .\
    <pre dir='ltr'>
      console.log(new set('jonasschmedtmann').size);
    </pre>
    نکته: اگر ترتیب آرایه ها برای ما اهمیت بیشتری نسبت به unique بودن مقادیر برامون داره میتوانیم از آرایه ها استفاده کنیم . ولی اگر unique بودن مقادیر اهمیت بیشتری نسبت به ترتیب مقادیر برامون داره بایستی از set استفاده کنیم .\
    مبحث نقشه ها:
    تفاوت بزرگ بین MAP و OBJECT ها در این است که  در MAP کلید ها میتوانند هر مقدار را داشته باشند ، اما در object ها کلید ها فقط می توانند رشته باشند .\
    <pre dir='ltr'>
      const rest = new Map();
      rest.set('name','pouria') // اولین مورد مربوط به مقدار کلید و دومین مورد مربوط به مقدار اختصاص داده شده به کلید می باشد
      rest.set(1,'firenze')
      rest.set(2,'Lisbon')
    </pre>
    نکته : هنگامی که یکی از دستورهای rest.set را هم log بگیریم نه تنها map ما را اپدیت نمیکند بلکه map کلی را هم برای ما برمیگرداند که این باعث می شود با لاگ گرفتن هر یک از دستورات به کل map هم دسترسی داشته باشیم .\
    ما حتی میتوانیم بیایم به صورت chaining تمامی map خود را اپدیت کنیم.\
    <pre dir='ltr'>
      rest.set('catgories',['italian','pizzeria']).set('open',11).set('close',13)
    </pre>
    در واقع ساز و کار مثال بالا ، به چه شکل است ، بدین شکل می شود که چون با هر بار set کردن map ما بروز می شود و به ما برگردانده میشود پس در نتیجه ما تمامی این مراحل انگار داریم به صورت تک به تک انجام میدهیم .\
    ما به وسیله متد  get می توانیم بیاییم و به مقادیر key در map ها دسترسی داشته باشیم .\
    <pre dir='ltr'>
      console.log(rest.get('name'));
    </pre>
    
    
    
    
    
    
    
    
    
    
    
     
     
    
    
    
    
    
  
    
    
    
    

    

  
    
</div>
