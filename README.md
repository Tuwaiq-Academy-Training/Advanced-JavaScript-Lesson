# Advanced-JavaScript-Lesson

# DOM مفهوم
 
DOM وهو اختصار Document Object Model
 وهو يعرض العناصر اللتي تمت كتابتها في واجهات المستخدم UI (ملفات HTML).

وكما هو موضح بالصوره يوجد لدينا شجرة DOM 

![DOM](https://paper-attachments.dropbox.com/s_DAF8495B9527B6244380D0BECA61ECAFD00DB0357A206D274592DE9435EE1DEE_1648376710649_DOM-01.png)


 
 
 بحيث في كل مره يتم عمل تغيير على ملف واجهات المستخدم (HTML) يقوم DOM بعمل تحديث على جميع العناصر وهذا قد يؤثر على سرعة العمل للتطبيق في حال كان لديك الكثير من العناصر. لنقل مثلا ان لديك اكثر من خمسين عنصر  في ملف HTML فهذا يعني انه سوف يقوم بتحديثها جميعها وهذا يؤثر في اداء التطبيق.


# Events and Event Listener مفهوم


تعتبر Events احداث تحدث عندما يتم تحفيزها من خلال triggers مثل الضغط على زر او تغيير قيمة عنصر ما، او حتى عند المرور mouse على عنصر ما وهو ما يسمى mouse hover.


## أمثلة على Events

يوجد العديد من الطرق لاضافة Events، احدى هذه الطرق هي باستخدام الخواص attributes الخاصّة بالعنصر tag نفسه كالتالي. 

**مثال**

    <html>
    <head>
        <title>Testing DOM Events</title>
    </head>
    <body>
        <h1 onclick="alert('alert')">hello</h1>
    </body>
    </html>

**المخرجات**

![](https://paper-attachments.dropbox.com/s_9B1E16265B7C987B67A6803250D6BB2EC80F9570947A6C48B759050871AAD864_1627147460922_Screen+Shot+1442-12-14+at+8.24.17+PM.png)


حين الضغط على النصّ سيظهر التالي:

![](https://paper-attachments.dropbox.com/s_9B1E16265B7C987B67A6803250D6BB2EC80F9570947A6C48B759050871AAD864_1627147750440_Screen+Shot+1442-12-14+at+8.29.03+PM.png)


الطريقة الثانية هي باستخدام الدالّة **getElementById** بحيث نقوم باسناد id للعنصر من ثمّ الوصول الى دالّة onClick من خلال المعرّف id الخاص بالعنصر كالتالي. 

**المثال**

    <html>
    <head>
        <title>Testing DOM Events</title>
    </head>
    <body>
        <h1 id="test">hello</h1>
        <script>
            document.getElementById('test').onclick = function(){
                alert('second alert');
            }
        </script>
    </body>
    </html>

**المخرجات**

![](https://paper-attachments.dropbox.com/s_9B1E16265B7C987B67A6803250D6BB2EC80F9570947A6C48B759050871AAD864_1627148593987_Screen+Shot+1442-12-14+at+8.43.10+PM.png)


ايضا، توجد طريقة ثالثة وهي باستخدام الدالّة addEventListener بحيث تستقبل هذه الدالّة نوع event من ثمّ ما يجب عليها عمله او تنفيذه ان حصل هذا الحدث event.

**المثال**

    <html>
    <head>
        <title>Testing DOM Events</title>
    </head>
    <body>
        <h1 id="test">hello</h1>
        <script>
            document.getElementById('test').addEventListener('click', function(){
                alert('second alert')}
                );
            
        </script>
    </body>
    </html>


**المخرجات**

![](https://paper-attachments.dropbox.com/s_9B1E16265B7C987B67A6803250D6BB2EC80F9570947A6C48B759050871AAD864_1627148879885_Screen+Shot+1442-12-14+at+8.47.55+PM.png)



كما ان الأحداث Events ليست محصورة فقط على onClick، يمكننا ايضا استخدام احد الأحداث في الجدول ادناه.

| نوع الحدث     | الوصف                                                     |
| ------------- | --------------------------------------------------------- |
| `dblclick`    | يتم تنفيذه عند النقر مرتين على زر الفأرة mouse.           |
| `mousemove`   | يتم تنفيذه تحرك الفأرة mouse.                             |
| `contextmenu` | يتم تنفيذة عندما يقوم المستخدم بمحاولة فتح context menue. |

> ملاحظة: ما تم ذكره اعلاه هي أنواع خاصّة في mouse، يوجد ايضا أنواع خاصة في keyboard مثل `keypress` و `keydown`. وانواع خاصّة في touch او network وغيرها.

أمثلة أخرى على الأنواع المذكورة.

**مثال** `dblclick`

    <html>
    <head>
        <title>Testing DOM Events</title>
    </head>
    <body>
        <h1 id="test">hello</h1>
        <script>
            document.getElementById('test').addEventListener('dblclick', function(){
                alert('hello world')}
                );
            
        </script>
    </body>
    </html>


**مثال** `mousemove`

    <html>
    <head>
        <title>Testing DOM Events</title>
    </head>
    <body>
        <h1 id="test">hello</h1>
        <script>
            document.getElementById('test').addEventListener('mousemove', function(){
                alert('hello world')}
                );
            
        </script>
    </body>
    </html>


**مثال**  `contextmenu` 

    <html>
    <head>
        <title>Testing DOM Events</title>
    </head>
    <body>
        <h1 id="test">hello</h1>
        <script>
            document.getElementById('test').addEventListener('contextmenu', function(){
                alert('hello world')}
                );
            
        </script>
    </body>
    </html>

