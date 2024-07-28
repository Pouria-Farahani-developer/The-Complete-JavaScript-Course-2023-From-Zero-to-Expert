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
      console.log(orderSet) //output ['ali','pouria','arman']
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
    
    

    

  
    
</div>
