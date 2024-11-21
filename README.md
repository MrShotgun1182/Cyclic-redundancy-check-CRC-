# Cyclic redundancy check (CRC) کد افزونگی دوره ای
### تکنیکی است برای شناسایی خطاها در داده های دیجیتال است. به عبارت دیگر از این کد برای تشخیص این که دیتایی که دریافت شده همان دیتایی باشد که ارسال شده است. که در مودم های ADSL, VDSL استفاده میشود. 
### نحوه کار کرد این الگوریتم به صورت یک هش (Hash) عمل میکند و برای هر باکس اطلاعاتی یک توالی کوتاه و با طول ثابت تولید میکند که به آن کد سی آر سی (CRC Code) گفته میشود. این کد سی آر سی (CRC Code) را همراه با بسته اطلاعاتی که ارسال میکند میفرستد، در سمت گیرنده دوباره برای بسته دریافت شده کد سی آر سی (CRC Code) تولید میکند و با کدی که از سمت فرستنده دریافت کرده است بررسی میکند، اگر کد سی آر سی (CRC Code) تولید شده برابر کد دریافت شده باشد یعنی دیتا به صورت درست دریافت شده است و اگر که کد سی آر سی (CRC Code) تولید شده با کدی که دریافت کرده است یکی نباشد به این معنا است که اطلاعات دوچار نویز شده است و باید از سمت فرستنده درخواست ارسال مجدد آن باکس اطلاعاتی را داشته باشد.
### ***نکته***: یک نکته مهم در مورد سی آر سی ها (CRC) این هست که راهکار مناسبی برای حفاظت در مقابل تغییرات عمدی روی داده نیستند. این به این معنا است که چون مبانی ساده ریاضیاتی در آن استفاده شده است باعث میشود که هر تغییر دلخواه را طوری روی داده ها اعمال کرد که کد سی آر سی (CRC Code) تولید شده تغییری نداشته باشد. 
### سه تا از سی آر سی های (CRC) پر کاربرد می توان به سی آر سی 16 بیت (CRC16)، سی آر سی 24 بیت (CRC24) و سی آر سی 32 (CRC32) اشاره کرد.
### برای شناخت بهتر الگوریتم های اعتبار سنجی اطلاعات بهتر است که با خطا هایی که احتمال دارد رو به رو شویم آشنا بشویم. 
# انواع خطا ها در ارسال اطلاعات:
- خطای یک بیت منفرد: تنها یک بیت وجود دارد که به نوعی از بین رفته باشد.
- خطای چند بیت: فریم درحالی دریافت میشود که بیش از یک بیت از بین رفته باشد.
- خطای گسترده: فریم شامل چندین بیت متوالی از داده ها است که از بین رفته اند.
### حال که با انواع خطا ها در ارسال یک فریم اطلاعات آشنا شدیم بیایید یک کد سی آر سی (CRC Code) تولید کنیم.
# ساخت کد سی آر سی (CRC Code):
### این تکنیک شامل تقسیم باینری بیت های داده ارسالی است. مقسوم با استفاده از معادله های چند جمله ای تشکیل میشود. فرستنده اطلاعات برای فریمی که قرار است ارسال کند این عمل را انجام داده و باقی مانده را محاسبه میکند. نتیجه به دست آمده را همراه با فریمی که قصد دارد ارسال کند، به یکدیگر متصل میکند و فریم حاصل شده را برای سمت دیگر ارسال میکند.
### زمانی که گیرنده اطلاعات را دریافت میکند قسمت کد سی آر سی را جدا میکند و با قسمتی که اطلاعات اصلی در آن بوده است برای خود یک بار دیگر کد سی آر سی (CRC Code) را تولید میکند و با کدی که از سمت فرستنده دریافت کرده است مقایسه میکند.
- در صورتی که کد های سی آر سی (CRC Code) یکسان باشند به این معنا است که اطلاعات به صورت کامل و صحیح انتقال داده شده اند و نویزی روی اطلاعات تاثیر نگذاشته است.
- اگر کد های سی آر سی (CRC Code) با یکدیگر مقایرت داشته باشند یعنی اطلاعات تحت تاثیر نویز قرار گرفته شده است و باید فریم اطلاعاتی دوباره از سوی فرستنده ارسال گردد.
![Alt text](https://blog.faradars.org/wp-content/uploads/2019/02/crc.jpg.webp)

