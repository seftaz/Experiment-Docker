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
## آراد جان برو تا تهش

</div>
