# Experiment-Docker
<div dir="rtl">

# بخش اول: استقرار با داکر
ابتدا پروژه base را روی ریپوی خود آوردیم.
### تصاویر مراحل کار:
- ![telegram-cloud-photo-size-4-5958298990783088378-y](https://github.com/seftaz/Experiment-Docker/assets/79265096/cff41ef7-7d5b-4baf-9692-c60b661b5d54)
  پروژه‌ی base


- ![telegram-cloud-photo-size-4-5958298990783088386-y](https://github.com/seftaz/Experiment-Docker/assets/79265096/8a8b958c-ff1c-4cf6-ae6c-575cf078f011)
فایل docker-compose.yml


- ![telegram-cloud-photo-size-4-5958298990783088387-y](https://github.com/seftaz/Experiment-Docker/assets/79265096/8d6674e8-5a9c-405e-b227-803a81f18de3)
فایل Dockerfile


- ![telegram-cloud-photo-size-4-5958298990783088388-y](https://github.com/seftaz/Experiment-Docker/assets/79265096/6b1dc7c2-8fb4-4dc7-a6ca-606a429ada39)
با توجه به دیتابیسی که در داکر تعریف شده، در فایل settings.py در اپ اصلی، مشخصات ارتباط با دیتابیس را ثبت می‌کنیم.


- ![telegram-cloud-photo-size-4-5958298990783088390-y](https://github.com/seftaz/Experiment-Docker/assets/79265096/ff0c89fb-b1f5-4278-8098-3f3eaefe9232)
نصب docker-compose


- ![telegram-cloud-photo-size-4-5958298990783088398-y](https://github.com/seftaz/Experiment-Docker/assets/79265096/a371f0c2-f330-4e3e-ac6b-7c8ae8e10550)
نصب داکر desktop


- ![telegram-cloud-photo-size-4-5958298990783088401-y](https://github.com/seftaz/Experiment-Docker/assets/79265096/93a483eb-727f-4812-93f5-44c8980ee70a)
ران کردن داکر کامپوز، شروع به pull کردن image های مورد استفاده مانند postgre


- ![telegram-cloud-photo-size-4-5958298990783088408-y](https://github.com/seftaz/Experiment-Docker/assets/79265096/c0c6a05d-9570-470a-8745-201f991a67d8)
ران شدن موفقیت آمیز، دو کانتینر برای وب سرویس و دیتابیس، و همچنین شبکه مربوط به اتصال


- ![telegram-cloud-photo-size-4-5958298990783088409-y](https://github.com/seftaz/Experiment-Docker/assets/79265096/dec501e4-3840-4d48-95f4-b1cffee79d39)
تصویر imageهای استفاده شده در docker desktop


- ![telegram-cloud-photo-size-4-5958298990783088410-y](https://github.com/seftaz/Experiment-Docker/assets/79265096/3b6b286a-6312-4144-8650-e01f72ec043f)
تصویر container مورد استفاده ما در docker desktop


- ![telegram-cloud-photo-size-4-5958298990783088413-y](https://github.com/seftaz/Experiment-Docker/assets/79265096/a57c28b6-d95a-4239-ba8d-3af499f1a786)
حال برای  ران کردن وب سرویس، باید به شکل بالا دستورات را وارد کنیم، با توجه به اروری که مشاهده می‌شود، باید تغییری در requriements بدهیم (اضافه کردن psycopg)، سپس دوباره داکر را بالا بیاوریم


- ![telegram-cloud-photo-size-4-5958298990783088415-y](https://github.com/seftaz/Experiment-Docker/assets/79265096/9eadc7a3-068a-4f9d-bb8b-c484cf549d06)
دوباره build کردن پروژه


- ![telegram-cloud-photo-size-4-5958298990783088416-y](https://github.com/seftaz/Experiment-Docker/assets/79265096/bf7409cc-2c98-48b4-a208-478b1227f95e)
انجام عملیات migrate


- ![telegram-cloud-photo-size-4-5958298990783088417-y](https://github.com/seftaz/Experiment-Docker/assets/79265096/df20934c-6526-45e4-bfad-8d3f62ec52a7)
دسترسی به پروژه روی پورت ۸۰۰۰


- ![telegram-cloud-photo-size-4-5958298990783088418-y](https://github.com/seftaz/Experiment-Docker/assets/79265096/c143cbf9-3a5b-4bc6-a4ca-8469cca1f35c)
ساخت سوپریوزر


- ![telegram-cloud-photo-size-4-5958298990783088419-y](https://github.com/seftaz/Experiment-Docker/assets/79265096/8124953e-eae6-42bc-a324-396b96fa63c1)
دسترسی و لاگین به اندپوینت admin با سوپریوزر تعریف شده



### وظیفه بخش‌های مختلف در پروژه:
#### DockerFile:
- تنظیم محیط پروژه Django
- نصب وابستگی‌ها از requirements.txt
- کپی فایل‌های پروژه به داخل کانتینر
#### docker-compose.yml:
- تعریف سرویس‌های پروژه: وب‌سرور Django و پایگاه‌داده PostgreSQL
- کانفیگ کردن نحوه ارتباط سرویس‌ها
- تنظیم پورت‌ها و وابستگی‌ها

# بخش دوم: استفاده از endpointها

پس از بیلد کردن پروژه با استفاده از دستور docker-compose up -d و ساخت migration ها، اقدام به ساخت superuser با دستور docker-compose exec web python manage.py createsuperuser میکنیم. سپس، با یوزر و پسورد داده شده، یوزر را میسازیم.

![image](https://github.com/seftaz/Experiment-Docker/assets/79263953/7e9d88d8-0e13-442d-aeef-f546fc0e1ab8)

اخطار پسورد ضعیف را نادیده میگیریم. لازم به ذکر است بدون ساخت و لاگین یوزر نمیتوان از API استفاده کرد زیرا پاسخ User is not logged in را دریافت میکنیم:

![image](https://github.com/seftaz/Experiment-Docker/assets/79263953/ad5c3b63-1b68-40f9-81b9-40d32377a602)

حال لازم است با یک دستور POST، به اکانت ساخته شده لاگین کنیم. ابتدا تابعی که API به آن میرود را بررسی میکنیم.

![image](https://github.com/seftaz/Experiment-Docker/assets/79263953/faee422c-76b8-4ea4-9c96-0580e4d0fd75)

میبینیم که دو attribute لازم برای اینکار username و password هستند. پس با postman درخواست لازم را ارسال میکنیم.

![image](https://github.com/seftaz/Experiment-Docker/assets/79263953/af290002-0580-4a67-8c4b-191879de160e)

پاسخ login successful را دریافت میکنیم. برای صحت سنجی یکبار دیگر notes را get میکنیم.

![image](https://github.com/seftaz/Experiment-Docker/assets/79263953/b9048a44-5c82-4623-8140-574f4cc7242b)

یک آرایه خالی دریافت میکنیم که درست است (دفع قبل user not legged in گرفتیم). حال کد تابعی که یادداشت ایجاد میکند را بررسی میکنیم.

![image](https://github.com/seftaz/Experiment-Docker/assets/79263953/49d21da5-e16a-4ee0-82e6-643e26276960)

همانطور که میبینید این تابع یک form-data دریافت میکند که با postman به راحتی قابل ارسال است. موارد گفته شده را وارد میکنیم:

![image](https://github.com/seftaz/Experiment-Docker/assets/79263953/12e023e4-7577-4d09-981b-602a8697fcca)

از پاسخی دریافتی تایید میشود که یادداشت ساخته شده است و زمان آن هم مشخص است. همین کار را برای یادداشت دوم میکنیم.

![image](https://github.com/seftaz/Experiment-Docker/assets/79263953/a25c7886-f013-4049-9be2-21d70155478e)

حال در API ای که برای دریافت یادداشت هاست get میکنیم.

![image](https://github.com/seftaz/Experiment-Docker/assets/79263953/57e76d85-a1f5-4c86-9812-ef58295404fa)

میبینیم که 2 یادداشت برگردانده شدند. حال تابع مرتبط به حذف یادداشت را باز میکنیم.

![image](https://github.com/seftaz/Experiment-Docker/assets/79263953/9594ba2d-6ca4-46ff-954f-2892bfeac08b)

میبینید که این تابع نوع درخواست را مشخص نکرده پس میتوان از همان get استفاده کرد. خروجی را در تصویر زیر میبینید:

![image](https://github.com/seftaz/Experiment-Docker/assets/79263953/d2389552-44ac-4e63-9f2a-0ccc9ea687e4)

حال دوباره تمام یادداشت هارا دریافت میکنیم.

![image](https://github.com/seftaz/Experiment-Docker/assets/79263953/e2827d0a-b59a-4e99-affc-e23af7e9d208)

همانطور که انتظار میرفت فقط یادداشت 2 برگردانده شد.

دستور docker ps و خروجی آن:

![image](https://github.com/seftaz/Experiment-Docker/assets/79263953/f294cae9-76a9-40a4-9c3c-d906446324df)

دستور docker-compose down

![image](https://github.com/seftaz/Experiment-Docker/assets/79263953/91152ec0-0e04-4c14-bda7-243b1886aaf2)



# پاسخ پرسش‌ها

وظایف Dockerfile، image و container را توضیح دهید.


**وظایف Dockerfile:**
- **تعریف محیط و دستورالعمل‌ها:** Dockerfile یک فایل متنی ساده است که حاوی مجموعه‌ای از دستورالعمل‌ها و پیکربندی‌ها برای ایجاد یک Docker image است. این دستورالعمل‌ها شامل نصب نرم‌افزارها، کپی فایل‌ها، تنظیمات محیطی و اجرای دستورات مورد نیاز برای راه‌اندازی نرم‌افزار هستند.
- **اتوماتیک‌سازی ساخت تصویر:** Dockerfile به توسعه‌دهندگان امکان می‌دهد که به صورت اتوماتیک و قابل تکرار، تصاویر Docker را بسازند. این فایل‌ها تضمین می‌کنند که محیط اجرایی در همه مراحل توسعه و تولید یکسان است.


**وظایف Image:**
- **حمل محیط اجرایی:** Docker image یک فایل فقط خواندنی و غیر قابل تغییر است که شامل همه چیزهایی است که برنامه برای اجرا نیاز دارد: کد برنامه، کتابخانه‌ها، وابستگی‌ها و تنظیمات محیطی.
- **قابل حمل و قابل توزیع:** تصاویر Docker قابل حمل هستند و می‌توانند بین سیستم‌های مختلف به اشتراک گذاشته شوند، به همین دلیل است که می‌توانند به راحتی در محیط‌های توسعه، تست و تولید استفاده شوند.
- **پایه‌گذاری کانتینرها:** هر کانتینر داکر از یک تصویر پایه‌گذاری می‌شود. یک تصویر می‌تواند چندین کانتینر را ایجاد کند و همه این کانتینرها مستقل از یکدیگر اجرا شوند.


**وظایف Container:**
- **اجرای نرم‌افزار در یک محیط ایزوله:** کانتینر یک محیط اجرایی سبک و ایزوله است که بر پایه یک Docker image ساخته شده است. کانتینرها تضمین می‌کنند که برنامه در یک محیط ثابت و ایزوله اجرا می‌شود.
- **مدیریت منابع:** کانتینرها از منابع سیستم مانند CPU، حافظه و فضای دیسک بهینه استفاده می‌کنند. آنها بسیار سبک‌تر از ماشین‌های مجازی (VM) هستند و به سرعت می‌توانند ایجاد، اجرا و متوقف شوند.
- **همگرایی محیط‌ها:** کانتینرها به توسعه‌دهندگان و مدیران سیستم اجازه می‌دهند تا اطمینان حاصل کنند که نرم‌افزار در همه محیط‌ها (توسعه، تست و تولید) به صورت یکسان اجرا می‌شود، بدون وابستگی به محیط خاصی.


از kubernetes برای انجام چه کارهایی می‌توان استفاده کرد؟ رابطه آن با داکر چیست؟

Kubernetes یک پلتفرم متن‌باز است که برای مدیریت و ارکستراسیون کانتینرها طراحی شده است. این پلتفرم به توسعه‌دهندگان و مدیران سیستم اجازه می‌دهد که برنامه‌های خود را به صورت مقیاس‌پذیر و قابل اعتماد در محیط‌های مختلف اجرا و مدیریت کنند. در ادامه به وظایف و کاربردهای Kubernetes و رابطه آن با Docker پرداخته می‌شود.

### کاربردهای Kubernetes

1. **ارکستراسیون کانتینرها:**
   - **مدیریت چندین کانتینر:** Kubernetes امکان مدیریت و هماهنگی تعداد زیادی از کانتینرها را در چندین میزبان فراهم می‌کند.
   - **خودکارسازی عملیات:** این پلتفرم می‌تواند فرآیندهایی مانند انتشار، مقیاس‌پذیری و بازیابی خودکار کانتینرها را خودکار کند.

2. **مقیاس‌پذیری:**
   - **مقیاس‌پذیری خودکار:** Kubernetes به طور خودکار می‌تواند تعداد کانتینرها را بر اساس بار کاری افزایش یا کاهش دهد.
   - **مقیاس‌پذیری دستی:** کاربران نیز می‌توانند به صورت دستی منابع را اضافه یا حذف کنند.

3. **تعادل بار (Load Balancing):**
   - **پخش بار کاری:** Kubernetes می‌تواند ترافیک ورودی را بین کانتینرها توزیع کند تا بار کاری به طور یکنواخت پخش شود و از عملکرد بهینه اطمینان حاصل شود.

4. **استقرار و بروزرسانی:**
   - **استقرار مداوم:** Kubernetes امکان استقرار نرم‌افزارهای جدید و بروزرسانی نسخه‌های موجود را بدون قطعی فراهم می‌کند.
   - **رول‌بک:** در صورت بروز مشکل، می‌توان به نسخه قبلی نرم‌افزار بازگشت.

5. **مدیریت ذخیره‌سازی:**
   - **ذخیره‌سازی پایدار:** Kubernetes از انواع سیستم‌های ذخیره‌سازی پشتیبانی می‌کند و می‌تواند به صورت پویا حجم‌های ذخیره‌سازی را به کانتینرها اختصاص دهد.
   - **ذخیره‌سازی ابری و محلی:** امکان استفاده از منابع ذخیره‌سازی محلی یا ابری را فراهم می‌کند.

6. **نظارت و لاگ‌گیری:**
   - **نظارت مداوم:** Kubernetes ابزارهای مختلفی برای نظارت بر عملکرد کانتینرها و کل سیستم دارد.
   - **جمع‌آوری و تحلیل لاگ‌ها:** امکان جمع‌آوری و تحلیل لاگ‌ها برای تشخیص و حل مشکلات فراهم است.

### رابطه Kubernetes با Docker

Kubernetes و Docker مکمل یکدیگر هستند و اغلب در کنار هم استفاده می‌شوند. رابطه این دو به صورت زیر است:

- **Docker به عنوان runtime کانتینر:** Docker یک فناوری runtime کانتینر است که کانتینرها را ایجاد و اجرا می‌کند. Kubernetes از Docker (و سایر runtimeهای کانتینر مانند containerd و CRI-O) برای اجرای کانتینرها استفاده می‌کند.
- **Kubernetes برای مدیریت کانتینرها:** در حالی که Docker به تنهایی برای اجرای یک یا چند کانتینر مناسب است، Kubernetes برای مدیریت و هماهنگی کانتینرها در مقیاس بزرگ و در چندین میزبان طراحی شده است.
- **Docker Compose vs. Kubernetes:** Docker Compose ابزاری است که برای تعریف و اجرای چندین کانتینر به صورت محلی استفاده می‌شود، اما Kubernetes برای مدیریت پیچیده‌تر و در مقیاس بزرگتر مناسب است.
- **زیرساخت مشترک:** Kubernetes می‌تواند کانتینرهای Docker را مدیریت کند و از آنها برای اجرای برنامه‌ها استفاده کند، اما به عنوان یک ارکستراتور پیشرفته، قابلیت‌های بیشتری نسبت به Docker به تنهایی دارد.



</div>
