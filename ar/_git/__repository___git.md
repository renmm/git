# الحصول على repository لمشروعك بـ Git

يمكنك انشاء مشروع بـ git بإحدى طريقتين. الأولى تكمن في أن تبدأ بناء على مشروع أسبق أو مجلد على سبيل المثال يحوي ملفات وأن تستورد مافيه الى مشروعك الجديد. أو أن تستنسخ repository بـ git جاهزة من مخدم ما.

## انشاء Repository في مجلد موجود مسبقاً

للبد بمتابعة تغيرات مشروع مسبق لديك بـ git، عليك الذهاب الى مجلد مشروعك ثم كتابة:

	$ git init

يقوم هذا بانشاء مجلد فرعية جديد تحت اسم .git يحوي جميع المعلومات والملفات المطلوبة - هيكل repository بـ git. حتى الآن، لن يتم متابعة أي تغيرات تحصل على مشروعك (انظر الفصل التاسع لمعلومات أخرى عن الملفات الموجودة في مجلد `.git` الذي أنشأته قبل قليل).

اذا أردت بمتابعة اصدارات الملفات الموجودة، يجب عليك البدء باخبار Git بهذه الملفات ومن ثم اجراء commit أولي. للقيام بهذا عليك استخدام أمر git add بالعدد الكافي بالملفات التي تريد، ومن ثم تتبعها أمر commit:

	$ git add *.c
	$ git add README
	$ git commit –m 'initial project version'

سنقوم بشرح هذه الأوامر في الفقرة القادمة، ولكن، الآن أصبحت التغيرات في مشروعك تتم متابعتها و commit أولي.

## استنساخ repository موجودة مسبقاً

للقيام باستنساخ  repository بـ git موجودة مسبقاً - مشروع تريد المساهمة فيه على سبيل المثال - الأمر الذي ستحتاجه هو git clone.  اذا كنت قد استخدمت أحد أنظمة إدارة الإصدارات الأخرى مثل Subversion مثلاً، ستلاحظ الإختلاف بين الأمر clone في git وأمر checkout. هناك فرق مهم، عندما تقوم git بعملية clone فإنك ستحصل على نسخة من كامل المعلومات تقريباً الموجودة على مخدم الـ repository. جميع إصدارات الملفات كلها في تاريخ حياة المشروع. أي، وبمعنى آخر، اذا حدث عطل أو ضرر ما لملفات المشروع الموجودة على المخدم الأساسي يمكنك استخدام أي واحدة من النسخ لاسترجاع المشروع للحالة التي كان عليها عند استنساخه (من الممكن أن تخسر بعض الروابط من طرف المخدم، ولكن جميع معلومات الإصدارات ستكون موجودة- انظر الفصل الرابع لمعلومات اخرى).


لاستنساخ repository يمكنك استخدام الأمر 'git clone [url]'. فعلى سبيل المثال، لكي تقوم باستنساخ مكتبة Git للغة Ruby والتي تدعى Grit، يمكنك القيام بالتالي:

	$ git clone git://github.com/schacon/grit.git

سيقوم هذا بانشاء مجلد جديد باسم "grit"، وتجهيز مجلد '.git' في داخله، سيقوم أيضاً بسحب جميع المعلومات من الـ repository، ويجهز نسخة جاهزة لكي تعمل عليها لآخر نسخة. اذا دخلت على مجلد 'grit' الجديد ستجد جميع ملفات المشروع. يمكنك بالطبع استنساخ المشروع لمجلد بإسم آخر، إليك مثال لكيفية القيام بهذا:

	$ git clone git://github.com/schacon/grit.git mygrit

سيقوم هذا الأمر بذات الأمر ولكن سيتم وضع المشروع بمجلد جديد باسم mygrit.

هناك عدد من البروتوكولات المختلفة التي يمكنك اسستعمالها لنقل المعلومات في git. المثال السابق يستعمل بروتوكول 'git://'، ولكن من الممكن أن تجد أيضاً استخداماً لـ 'http(s)://' أو 'user@server:/path.git'، والتي تستعمل بروتوكول SSH في النقل. في الفصل الرابع من الكتاب ستتعرف على الخيارات المتوفرة للتواصل مع الـ repository الخاصة بك وميزات ومساوئ كل منها.