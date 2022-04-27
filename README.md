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



# بعض أمثلة Array methods

# دالة concat

أثناء التعامل مع المصفوفات قد ترغب في دمج أكثر من مصفوفة معاً. مثلاً في المثال أدناه مصفوفتين كل مصفوفة مكونة من مجموعة من الألوان، وفي حال أردنا دمج تلك المصفوفتين توفر لنا لغة Javascript دالة `concat` والتي تستخدم لدمج مصفوفتين أو أكثر دون التأثير على المصفوفات الموجودة، أي تقوم بترجيع مصفوفة جديدة مكونة من جميع عناصر المصفوفات التي أردنا دمجها.


    const primaryColors = ['red', 'yellow', 'blue']
    const secondaryColors = ['green', 'orange', 'violet']

سنقوم الآن بدمج المصفوفتين `primaryColors` و `secondaryColors` بداخل مصفوفة جديدة باسم `colors` عن طريق تحديد اسم المصفوفة الأولى ثم استخدام الدالة `concat` مع إعطائها اسم المصفوفة الثانية بالشكل التالي:


    const primaryColors = ['red', 'yellow', 'blue']
    const secondaryColors = ['green', 'orange', 'violet']
    const colors = primaryColors.concat(secondaryColors)
    
    console.log(colors) //output: [ 'red', 'yellow', 'blue', 'green', 'orange', 'violet' ]

في المثال أعلاه تم دمج عناصر المصفوفة الأولى `['red', 'yellow', 'blue']` مع عناصر المصفوفة الثانية `['green', 'orange', 'violet']` وعند طباعة المصفوفة الجديدة أصبحت المخرجات كالتالي:


    //output: [ 'red', 'yellow', 'blue', 'green', 'orange', 'violet' ]


# دالة filter

لنفترض أن لدينا مصفوفة ونريد أن نقوم بالبحث عن عناصر معينة من هذهِ المصفوفة وتخزينها في مصفوفة جديدة. توفر لنا لغة JavaScript دالة باسم `filter` تساعدنا في هذا الغرض، بحيث تقوم هذهِ الدالة بفلترة عناصر المصفوفة بناءً على شرط معين وتخزين العناصر التي تطابق الشرط في مصفوفة جديدة.

    const numbers = [2, 3, 7, 4, 9]

لدينا هنا مصفوفة مكونة من أرقام، سنقوم بتطبيق دالة `filter` عليها لاستخراج **الأعداد الزوجية** وتخزينها في مصفوفة جديدة، الدالة `filter` يمرر لها 3 قيم بحيث أن المدخل الأول هو العنصر الحالي (ابتداءً من العنصر 2 وحتى العنصر 9)، المدخل الثاني هو قيمة index للعنصر الحالي، وأخيرًا المدخل الثالث هو المصفوفة.

    const numbers = [2, 3, 7, 4, 9]
    
    const evenNumbers = numbers.filter(function(currentValue, index, array) {
        return currentValue % 2 === 0
    })

في المثال أعلاه الشرط الذي بداخل الدالة `filter` سيتم تطبيقه على جميع عناصر المصفوفة عنصر ويليه العنصر الآخر، مثلًا سيتم أولًا أخذ العنصر الأول 2 ثم سيتم اختبار الشرط عليه، هل باقي قسمة العدد 2 على 2 يساوي الصفر؟ إذا كان الجواب **نعم** سيتم تخزين العدد 2 بداخل مصفوفة باسم `evenNumbers` ثم الانتقال للعنصر التالي، أما إذا كان الجواب **لا** سيتم الانتقال للعنصر الآخر مباشرة دون تخزين العدد في المصفوفة الجديدة `evenNumbers`.


# دالة find

لنفترض أن لدينا مصفوفة تتكون من عدة عناصر، ونريد أن نحصل على أول عنصر الذي يطبق شرط معين، سنقوم الآن بتطبيقها باستخدام `if statement`.

    const numbers = [11, 7, 9, 15]
    
    for(let i = 0; i <= numbers.length; i++){
        if(numbers[i]%3 === 0){
            console.log(numbers[i])
            break;
        }
    }

 في Javascript بإمكاننا استخدام الدالة `find` لنفس الغرض وبشكل أبسط وأقصر في الكتابة. بحيث أن هذه الدالة تقوم بترجيع **أول عنصر** ينطبق عليه الشرط الذي تم وضعه. هذه الدالة تستقبل `callback` `function` تستدعيها في كل مرة تمر على أحد عناصر المصفوفة `numbers` وتقوم باختبار الشرط على هذا العنصر، في حال طابق الشرط ستقوم بترجيع قيمته.

    const numbers = [11, 7, 9, 15]
    
    const el = numbers.find(function(element) {
        return element % 3 === 0
    })

في المثال أعلاه تم تطبيق الدالة `find` على المصفوفة `numbers`. تستقبل `Callback function` وتتنفذ على كل عنصر من المصفوفة، مما يعني سيتم أخذ أول عنصر `11` ثم سيتم التحقق منه، هل يقبل القسمة على 3؟ إذا كان **نعم** سيتم تخزين قيمته في الثابت `el` ويتوقف التنفيذ. أما إذا كان **لا** سيتم الانتقال للعنصر الذي يليه.
الآن القيمة المخزنة بداخل الثابت `el` هي `9` لأنه أول عدد في المصفوفة يقبل القسمة على 3. 



# دالة forEach

عند التعامل مع المصفوفات قد تحتاج إلى طباعة عناصرها بالكامل، في المثال التالي مصفوفة من ٣ عناصر وتم المرور على تلك العناصر من خلال `for loop` لطباعتها:

    const colors = ['red', 'green', 'blue']
    for(let i = 0; i < colors.length; i++){
        console.log(colors[i])
    }

المخرجات:

    red
    green
    blue

هناك أيضًا دوال للتعامل مع المصفوفات بشكل خاص، تساعد في المرور على عناصر المصفوفة وتطبيق أي عملية عليها، مثل دالة `forEach`. هذه الدالة تستقبل callback function تقبل ما بين مدخل إلى ثلاث مدخلات بحيث أن: 

- المدخل الأول: يمثل العنصر الحالي التي تمر عليه الدالة، لأنها تبدأ من أول عنصر وفي كل مرة تنتقل للعنصر الذي يليه لتطبق عليه عملية ما.
- المدخل الثاني: يمثل index الخاص بالعنصر الحالي التي تمر الدالة عليه.
- المدخل الثالث: المصفوفة نفسها.

سنقوم الآن بتطبيقها على المصفوفة `colors`. 

    const colors = ['red', 'green', 'blue']
    
    colors.forEach((currentValue, index, array) => {
        console.log(index, currentValue)
    })

في المثال أعلاه تم تطبيق دالة `forEach` على المصفوفة `colors.forEach` ومن ثم تم تحديد ٣ مدخلات وهي العنصر، عنوان العنصر index والمصفوفة. وبداخل الدالة تم طباعة عنوان العنصر مع محتوى العنصر، بحيث أن الدالة `forEach` ستقوم أولاً بالمرور على العنصر الأول، طباعة عنوانه `0` مع محتواه `red` ثم تنتقل للعنصر الآخر وهكذا إلى أن تنتهي عناصر المصفوفة. المخرجات ستكون كالتالي:

    0 red
    1 green
    2 blue



# دالة includes
لنفترض أن لدينا مصفوفة معينة، ونريد البحث عن عنصر ما إن كان متواجد في تلك المصفوفة أم لا. هناك دالة `includes` تساعدك في هذا الغرض، لنفترص أن لدينا المصفوفة التالية:

    // index          0       1       2    
    const colors = ['red', 'green', 'blue']

ونريد البحث هل هذه المصفوفة تحتوي على العنصر `red` أم لا، سنقوم باستخدام دالة `includes` ونقوم بإعطائها القيمة `red` لتقوم بالبحث عنها. ولأن الدالة includes ترجع قيمة boolean (أي T*rue* في حال وجدت العنصر و F*alse* في حال لم تجد العنصر) سنقوم بتعريف متغير باسم `containsRed` لتخزين قيمة مخرج الدالة.

    // index          0       1       2    
    const colors = ['red', 'green', 'blue']
    const isContainRed = colors.includes('red')
    console.log(isContainRed) //output: true

المخرج من عملية البحث في المثال السابق `true` لأن العنصر `red` موجود فعليًا في المصفوفة `colors`.
الدالة `includes` من الممكن أن تستقبل مدخل آخر غير قيمة العنصر الذي ستبحث عنه، وهو قيمة index للبدء في عملية البحث، مثلاً نستطيع أن نطلب من الدالة القيام بالبحث عن العنصر `red` ابتداءً من `index = 1` بالشكل التالي:

    // index          0       1       2    
    const colors = ['red', 'green', 'blue']
    const isContainRed = colors.includes('red', 1)
    console.log(isContainRed) //output: false

في هذه الحالة سيكون المخرج False لأن العنصر red موجود في index = 0 والدالة `includes` قامت بتخطي index = 0 وبدأت من عند index = 1.



# دالة Join

لنفترض أنه لدينا مصفوفة ما، ونريد جمع عناصر تلك المصفوفة بداخل نص `String`. في هذه الحالة توفر لغة Javascript دالة `Join` والتي تقوم بإنشاء وترجيع نص جديد يتكون من عناصر المصفوفة مفصولة بفاصلة (Comma) أو أي رمز آخر. في المثال التالي لدينا مصفوفة باسم `arrColors`:

    const arrColors = ['red', 'green', 'blue']

الدالة `Join` تستقبل مُدخل رمز **اختياري** والذي يمثل الفواصل بين عناصر المصفوفة بداخل النص. بحيث أنه إذا لم يتم إعطاء الرمز للدالة ستقوم الدالة بوضع فاصلة بين كل عنصر والآخر ويصبح شكل النص كالتالي `red,green,blue`، وفي حال كان المُدخل عبارة عن نص فارغ سيتم جمع عناصر المصفوفة دون أي رمز بينهما. سنقوم الآن بجمع عناصر المصفوفة `arrColors` باستخدام الدالة `Join` دون إعطائها أي مُدخل بداخل نص جديد باسم `strColors`.


    const arrColors = ['red', 'green', 'blue']
    const strColors = arrColors.join()
    console.log(strColors) //output: red,green,blue

بما أنه لم يتم إعطاء أي مدخل للدالة `Join` ستقوم بوضع فاصلة بين كل عنصر والآخر، وستكون المخرجات كالتالي:


    //output: red,green,blue

الآن سنقوم بإعطاء الدالة مُدخل **نص فارغ** مما يجعلها تقوم بجمع العناصر دون أي رمز بينهما، كما يلي:


    const arrColors = ['red', 'green', 'blue']
    const strColors = arrColors.join('')
    console.log(strColors) //outpt: redgreenblue

أصبحت العناصر متلاصقة بداخل النص بالشكل التالي:


    //outpt: redgreenblue

الآن، سنقوم بإعطاء الدالة مُدخل نص وبداخله مسافة (whitespace) حتى تقوم بوضع مسافة بين كل عنصر والآخر بداخل النص. 


    const arrColors = ['red', 'green', 'blue']
    const strColors = arrColors.join(' ')
    console.log(strColors) //output: red green blue

عندها ستصبح المخرجات كما يلي:

    //output: red green blue



# دالة map

عند التعامل مع المصفوفات من أكثر التطبيقات عليها هو المرور على عناصرها ومن ثم تطبيق بعض العمليات عليها. من أكثر الدوال استخدامًا لهذا الغرض هي الدالة `map` والتي ينتج عنها **مصفوفة جديدة** مكونة من عناصر *مصفوفة أخرى* لكن بعد تطبيق بعض العمليات على كل عنصر منها. مثلاً في المثال أدناه مصفوفة مكونة من عدة أرقام نريد ضرب كل عنصر من تلك المصفوفة في العدد ٢:

    const array1 = [1, 4, 9, 16];

من الممكن الاستعانة بالدالة `map` لضرب كل عنصر بالعدد ٢ ومن ثم تخزين هذا العنصر في مصفوفة جديدة. ثم الانتقال للعنصر الآخر وتكرار نفس الخطوات. الدالة `map` تستقبل callback function والتي بدورها تستقبل ٣ مدخلات وهي currentValue, index, array. نحتاج هنا فقط currentValue والذي يمثل العنصر الحالي الذي تمر عليه الدالة `map` 
من المصفوفة `array1`. بحيث أنها تبدأ من العنصر الأول، أي أن قيمة currentValue في المرة الأولى=1، تضرب هذا العنصر في العدد ٢ ثم تنتقل للعنصر الآخر وهكذا. 


    const array1 = [1, 4, 9, 16];
    const map1 = array1.map(function(currentValue) {  
      return currentValue * 2
    })
    console.log(map1) //output: [ 2, 8, 18, 32 ]

إذًا باختصار الدالة `map` قامت بالمرور على جميع عناصر المصفوفة `array` وتطبيق عملية الضرب بالعدد 2 على جميع العناصر، وتخزين هذه العناصر في مصفوفة جديدة باسم `map1`. فأصبحت المخرجات كالتالي:


    //output: [ 2, 8, 18, 32 ]

هناك طريقة أبسط وأقصر في تنفيذ هذه العملية، وهي استخدام `Arrow function` مع الدالة `map` كما في المثال أدناه:


    const array1 = [1, 4, 9, 16];
    const map1 = array1.map(x => x * 2);
    console.log(map1);

نلاحظ أن المثال أصبح أقصر وأبسط في القراءة دون التأثير على المخرجات.


    //output: [ 2, 8, 18, 32 ]


# دالة reverse

لنفترض أن لدينا المصفوفة التالية مكونة من أرقام مكتوبة تصاعديًا، ونريد عكسها أو تخزينها بشكل تنازلي:

    const numbers = [1, 2, 3, 4, 5]

في هذه الحالة تساعدنا الدالة `reverse` في هذا الغرض، والتي تستخدم لعكس عناصر المصفوفة نفسها دون إنشاء مصفوفة جديدة.

    const numbers = [1, 2, 3, 4, 5]
    numbers.reverse()
    console.log(numbers) //output: [ 5, 4, 3, 2, 1 ]

بهذا الشكل تم عكس جمع عناصر المصفوفة `numbers` باستخدام الدالة `reverse` ليصبح شكل المصفوفة كالتالي:

    //output: [ 5, 4, 3, 2, 1 ]


# دالة split
لنفترض أن لدينا نص `string` معين ونريد تقسيم هذا النص إلى عناصر بداخل مصفوفة.

    const strColors = 'red green blue black'

توفر لغة Javascript دالة `split` والتي تقوم بتقسيم النص على عدة أقسام نصية مرتبة وتخزينها في مصفوفة جديدة. الآن سنقوم بتقسيم النص `strColor` إلى عدة ألوان، بحيث كل لون يمثل عنصر بداخل مصفوفة جديدة باسم `arrColors` بالشكل التالي:


    const strColors = 'red green blue black'
    const arrColors = strColors.split(' ')
    console.log(arrColors) //output: [ 'red', 'green', 'blue', 'black' ]

 
 في المثال أعلاه، قمنا بإعطاء الدالة `split` مُدخل علامات تنصيص بداخلها مسافة `whitespace`، وهذا يعني أن الدالة ستقوم بأخذ النص حتى ترى مسافة `whitespace`، ستتوقف وتخزن النص كعنصر في المصفوفة، وتقوم بالاستمرار بعد المسافة في أخذ نص جديد لتخزينه كعنصر في المصفوفة. وهذا يعني أنها ستأخذ الكلمة `red` بعدها سترى مسافة فتتوقف وتقوم بتخزين الكلمة `red` كعنصر في المصفوفة، ثم تكمل بعد المسافة وتأخذ الكلمة `green` وتخزنها في المصفوفة، وهكذا حتى تنتهي من النص `strColors`، فتصبح المخرجات كالتالي:
 

    //output: [ 'red', 'green', 'blue', 'black' ]

إذًا الدالة `split` نقوم بإعطائها المُدخل الذي نريد منها أن تتوقف عنده بداخل النص والاستمرار من بعده. مثلاً لو كان النص لدينا كما في المثال التالي، ونريد تخزين كل لون على حِده:


    const strColors = 'red ; green ; blue ; black'

سنقوم بإعطاء الدالة المُدخل `;` حتى تتمكن من أخذ كل لون على شكل عنصر في المصفوفة الجديدة بالشكل التالي: 


    const strColors = 'red ; green ; blue ; black'
    const arrColors = strColors.split(' ; ')
    console.log(arrColors) //output: [ 'red', 'green', 'blue', 'black' ]

كما نستطيع أن نخبر الدالة `split` أن تتوقف بعد أخذ عدد معين من العناصر، وذلك عن طريق إعطائها مدخل آخر يمثل عدد العناصر التي ستتوقف بعد تخزينها. فإن أردنا تخزين فقط أول لونين `red` و `green` سنقوم بإعطائها العدد ٢ كالتالي:


     const strColors = 'red ; green ; blue ; black'
     const arrColors = strColors.split(' ; ', 2)
     console.log(arrColors) //output: [ 'red', 'green' ]



# مفهوم Promises
توجد مشكلة لدى استخدامنا لمفهوم Asynchronous، وهي اعتماديّة العمليّات ذات الوقت القليل على العمليّات ذات الوقت الطويل. ولحل هذه المشكلة نستطيع استخدام مفهوم callback. لكن واجهتنا مشكلة أخرى في مفهوم callbacks و هو أنه سيزيد من تعقيد البرنامج في حالة تواجد العديد من العمليّات التي تعتمد على بعضها. بالتالي اتى مفهوم promises. يعتبر مفهوم promises مجرّد طريقة أخرى للتعامل مع Asynchronous code. بحيث يَعِد - promise - بالقيام بعمليّةِِ ما. لذلك promise في javascript عبارة عن object له مسارين، مسار يتحقق عندما تتنفذ العمليّة المسندة ومسار يتحقق عن فشلها.

![](https://paper-attachments.dropbox.com/s_4CEF2DAD214A47924564C05FBF9C2B006FDC43AB20145A176D3422605608588B_1627233482362_Screen+Shot+1442-12-15+at+8.17.58+PM.png)


لنأخذ مثال على طريقة كتابة promise في javascript .

**مثال**

    console.log('Start')
    const nweUser = new Promise((resolve, reject) => {
        setTimeout(() => {
            const userInfo = {
                name: 'Khalid',
                age: 19
            }
            resolve(userInfo)
        }, 3000)
    });

بالمثال اعلاه، قمنا بانشاء promise جديد له مدخلين، الأول ما يجب عملة عندما تكتمل العمليّة resolved والآخر هو ما يجب عملة عندما تفشل العمليّة reject. كلاً من resolved و reject يمثّلون callbacks وطريقة ارسالهم تكون من خلال استخدامنا للكلمة then و catch. فعندما نريد وصف ما يجب عملة عند نجاة العمليّة - resolved - سنقوم باستخدام then كالتالي. 


    console.log('Start')
    const nweUser = new Promise((resolve, reject) => {
        setTimeout(() => {
            const userInfo = {
                name: 'Khalid',
                age: 19
            }
            resolve(userInfo)
        }, 3000)
    });
    nweUser.then(res => {
            console.log('** User info received **')
            console.log(res) })
    console.log('END')

يمثّل  `res`  البيانات المرسلة من دالّة resolved وهي userInfo.

**المخرجات**

    Start
    END
    ** User info received **
    { name: 'Khalid', age: 19 }

بالمثال أعلاه، تعلمنا كيف نتعامل مع النتيجة عندما يتم تنفيذ العمليّة بنجاح، لكن ماذا اذا حدث خطأ؟ في حالة حدوث خطأ نستطيع استخدام catch بحيث نتعامل مع الخطأ الظاهر كالتالي.

    console.log('Start')
    const nweUser = new Promise((resolve, reject) => {
        setTimeout(() => {
            const userInfo = {
                name: 'Khalid',
                age: 19
            }
            resolve(userInfo)
        }, 3000)
    });
    nweUser.then(res => {
            console.log('** User info received **')
            console.log(res) })
            .catch(err=> console.log(`the error message is:${err.message}`));
    console.log('END')

الآن، في حالة حدوث خطأ ستتم طباعة النّص  `:the error message is`   من ثمّ رسالة الخطأ.


# مفهوم async/await

 هناك بنية خاصة للعمل مع الوعود بطريقة أكثر راحة ، تسمى “async / await”. من السهل جدًا فهمها واستخدامها.


## مفهوم async 
لنبدأ بالكلمة الرئيسية async. يمكن وضعها قبل دالة ، مثل هذا:

    async function f() {
    return 1;
    }
    
    

## مفهوم await
لا يمكن إستخدام await إلا بداخل async 
الصيغة:


let value = await promise;


 
تجعل الكلمة الرئيسية await جافا سكريبت تنتظر حتى يتنفذ هذا الوعد ويعيد نتيجته.


# مفهوم callback

في مفهوم Asynchronous ذكرنا أنه يقوم بتنفيذ العمليّات بشكل غير متزامن بحيث أن العمليّات التي تأخذ وقت في التنفيذ يقوم بتأجيلها وتنفيذ العمليّات التي لا تأخذ وقت، وبهذا الشكل نحن نزيد من سرعة التنفيذ، لكن السؤال هنا هو ماذا إذا وجدت عمليّات تعتمد على العمليّة التي تأخد وقت؟ بمعنى ماذا إذا انتقل التنفيذ إلى عمليّة تعتمد على نتيجة عمليّة أخرى ذات وقت أطول وتم تأجيلها! لنأخذ مثال برمجي على ذلك. 

**مثال**:
****
    console.log('Start')
    function userInfo(name) {
        setTimeout(() => {
            console.log('** User info received **')
            return name
        }, 3000)
    }
    let userName = userInfo('Khalid')
    console.log(userName)//undefined
    console.log('End')

هنا نلاحظ أن المتغيّر userName يعتمد على الدالة userInfo، وهذهِ الدالة تأخذ ثلاث ثواني للتنفيذ، بمعنى أن جملة الإسناد ستتنفذ قبل أن تعود القيمة من الدالة بالتالي سيكون نتيجة جملة الطباعة بالسطر قبل الأخير `undefined`. 

**المخرجات**:

    Start
    undefined
    End
    ** User info received **

السبب من عدم وجود قيمة للمتغير userName هو اعتمادية عمليّة الإسناد على الدالة التي تقوم بالتنفيذ لوقت طويل، وأحد الحلول الممكنة لحل مشكلة الاعتماديّة هي استخدام مفهوم callback، ويعتبر callback مجرّد دالة مرسلة كمدخل لدالة أخرى، بحيث يصف للدالة الأخرى مايجب فعله عند انتهائها من التنفيذ، وفي مثالنا السابق سنقوم بإرسال دالة تقوم بعملية طباعة اسم المستخدم كمدخل للدالة userInfo. 

**المثال**:

    console.log('Start')
    function userInfo(name, callback) {
            setTimeout(() => {
                console.log('** User info received **')
                callback(name)
            }, 3000)
        }
        let userName = userInfo('Khalid', name => {
            console.log(`Your name is ${name}`)
        })
    console.log('End')

نلاحظ أننا هنا قمنا بإضافة parameter آخر يدعى callback، ويمثّل الدالة التي سنقوم بإرسالها، وعند استدعائنا للدالة سنقوم بوضع العمليّات التي تعتمد عليها في body لتنفيذها، وفي حالتنا هي عمليّة طباعة الاسم.  

> ملاحظة: يمكنك تسمية parameter بأي اسم آخر لكن المتعارف عليه هو تسميته callback. 


**المخرجات**:

    Start
    End
    ** User info received **
    Your name is Khalid

يعتبر callback أحد الحلول الممكنة للتعامل مع مشكلة الاعتماديّة بين العمليّات، لكن بهذهِ الطريقة عندما يكون لدينا عدد كبير من العمليّات سيزيد عدد callbacks الموجودة في البرنامج وسيؤدي ذلك إلى تعقيده أكثر لذلك وجد مفهوم promises. 



# مفهوم Synchronous و Asynchronous

تقوم عادةً لغات البرمجة بتنفيذ خطوة أو تعليمة من ثم التعليمة الأخرى وهكذا، أي بالترتيب sequence، لنرى المثال التالي في لغة Javascript.

**مثال**:
****
    console.log(1);
    console.log(2);
    console.log(3);
    console.log(4);
    console.log(5);

**المخرجات**:

    1
    2
    3
    4
    5

نلاحظ أن التعليمات تمت طباعتها بالترتيب، أي أنه تم تنفيذ جملة الطباعة الأولى ومن ثمّ الثانية بالترتيب إلى الخامسة، وتسمى طريقة التنفيذ هذهِ Synchronous أي أن التعليمات تتنفذ واحدة تلوى الأخرى ولا ينتقل التنفيذ للتعليمة الأخرى إلّا حين انتهاء التعليمة السابقة، لكن السؤال الآن ماذا إذا اخذت أحد العمليّات وقت أطول بالتنفيذ؟ كمثال لنفترض وجود صف للحساب في supermarket والذي أمامك لديه سلتين بينما لديك غرض واحد فقط لحسابه، أنت الآن مجبر على الانتظار إلى أن ينتهي الشخص أمامك من الحساب. أترى إشكاليّة بذلك؟ كان بامكانهم حفظ الوقت من خلال تنفيذ عمليتك بالأول من ثمّ اكمال عمليّة الشخص الآخر، ومن هنا وجدت آليّة أخرى وهي ما يعرف بمسمّى Asynchronous، بحيث تنص على ان العمليّات التي تأخذ وقت سيتم تأجيلها الى أن تنتهي من التنفيذ، لنأخذ مثال برمجي على ذلك، بافتراض أن العملية الثانية (جملة الطباعة الثانية) ستأخذ ثلاثة ثواني للتنفيذ. 

**مثال**:

    console.log(1);
    setTimeout(() => {
      console.log(2);  
    }, 3000);
    console.log(3);
    console.log(4);
    console.log(5);

**المخرجات**:

    1
    3
    4
    5
    2

 نلاحظ بالمخرجات أنه تمّ تنفيذ جمل الطباعة بالترتيب ما عدى الثانية، بحيث أنه تم تأجيلها إلى حين انتهاء وقت الانتظار 
 (ثلاثة ثواني) من ثم تم تنفيذها.
 
 



