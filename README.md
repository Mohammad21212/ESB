
گام اول
در گام اول الزم است که با هر زبان برنامه نویسی که تجربه دارید یک پروژه ایجاد کنید و API با شرح زیر را توسعه دهید.
در پروژه مورد نظر یک API توسعه دهید که یک مقدار عددی )number )از URL درخواست/ورودی و یک UUID از Header
درخواست با نام id و ارایهی JSON در Payload/Body درخواست دریافت کند. پس از دریافت مقادیر ذکر شده، با تطبیق
مقادیر number با BodyIdNumber و id با BodyId مربوط به Objectهای موجود در ارایهی ورودی، در خروجی Objectهای
تطبیق داده شده را برگرداند و در صورت عدم تطابق Object، در خروجی خطای مشخص شده را برگرداند.
POST /api/test/{dynamic number} HTTP/1.1
Header : id = {dynamic uuid}
Input Body :
[
{
"BodyId": "{uuid}",
"BodyIdNumber": "{number string}",
"name": "{name string}"
},
{
"BodyId": "{uuid}",
"BodyIdNumber": "{number string}",
"name": "{name string}"
}
]
Error Output :
{
"message": "not found"
}
گام دوم
نصب پیشنیازها)مطابق با آموزشهای ارائه شده(
- نصب و راه اندازی Java
- نصب و راه اندازی Maven
- نصب و راه اندازی MI 2Wso
توسعه یک API با مشخصات زیر بر روی MI 2Wso(مطابق با آموزشهای ارائه شده(
یک API توسعه دهید که یک مقدار عددی )number )و یک uuid با نام id از Param Query درخواست و یک ارایهی JSON
در بدنه)Body/Payload )درخواست دریافت کند و با تطبیق مقادیر number با BodyIdNumber و id با BodyId
Objectهای ارایهی ورودی، درخروجی فقط فیلد name از ابجکت انتخاب شده با 200 = Code Status HTTP برگردانده
شود و در صورت عدم تطابق Object در خروجی خطای مشخص شده با 400 = Status HTTP را برگرداند.
POST /api/training/v1.0?number={dynamic number}&id ={dynamic uuid} HTTP/1.1
Input Body :
[
{
"BodyId": "{uuid}",
"BodyIdNumber": "{number string}",
"name": "{name string}"
},
{
"BodyId": "{uuid}",
"BodyIdNumber": "{number string}",
"name": "{name string}"
}
]
Success Output with HTTP status code 200:
{
"name": "{name from found object}"
}
Error Output with HTTP status code 404:
{
"message": "not found"
}
نکتهها
- قرار دادن Code Source بر روی git امتیاز محسوب میشود.
- ارسال فایل Postman سرویسهای توسعه داده الزامی است.
- منابع آموزشی برای برخی موارد فوق ارائه شده است و در صورت لزوم مورد استفاده قرار گیرد
