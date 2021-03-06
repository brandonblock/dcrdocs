# دليل تشغيل dcrd

آخر تحديث له كان v1.0.0.

هذا الدليل معد للمساعدة على تشغيل تطبيق `dcrd` وذلك بإستخدام [أعلام بدء التشغيل](/getting-started/startup-basics.md#startup-command-flags).

**Prerequisites:**

- استخدام أخر  [dcr تثبيت](/getting-started/user-guides/cli-installation.md) وذلك ليتم تثبيت `dcrd`.  بالإضافة إلى خطوات التي تتطلب إستخدام طريقة تثبيت جديدة.
- قم بمراجعة إطلاق الأوامر لموجه الأوامر  (Windows)و Bash (macOS/Linux)  وقد تختلف  [هنا] (/getting-started/cli-differences.md).

---

`dcrd` هو العقد الخفي ل Decred. أي هو البرنامج الذي يعمل في الخلفية التي لم تكن ذات واجهة مباشرة. `dcrd` يحافظ على دفتر كامل من المعاملات السابقة (أو سلسلة كتلة) الخاصة ب Decred. بحيث يسمح بترحيل المعاملات الى عقد Decred في جميع أنحاء العالم. ويمكنك التفكير بها بطريقتك الخاصة حول خدمات سلسلة الكتل ل Decred. ونجد أن سلسلة الكتل تحفظ الملفات من حيث  `تاريخ` بدون `dcrd` أي الدليل الرئيسي.

**المستخدمين المتقدمين: إذا كنت تقوم بتشغيل في وضع عبر SSH,** فإنك سوف تحتاج لإستخدام محطات متعددة مثل  [شاشة](h tp://www.howtogeek.com/howto/ubuntu/keep-your-ssh-session-running-when-you-disconnect/) أو  [tmux](https://tmux.github.io/). حيث يمكنك رؤية تعليمات للتحرك لغلاف اخر, وسوف تحتاج للبدء بنافذة ويندوز جديدة في `screen`أو  `tmux`.

---

## <i class="fa fa-cloud"></i> التواصل مع شبكة Decred

في المرة الأولى لإطلاق  `dcrd` ستتمكن من التواصل مع شبكة Decred, والبدء في تحميل سلسلة الكتل. بحيث يسمح `dcrwallet` و  `dcrctl` للتواصل مع `dcrd`,يجب أن تحتوي ملفات التكوين على `rpcuser` و` rpcpass`أي إعدادات ممكنة.

> تكوين اسم المستخدم وكلمة المرور RPC

إذا إستخدمت [`dcr تثبيت`](/getting-started/user-guides/cli-installation.md), يتم بالفعل إعداد ملفات التهيئة باستخدام اسم مستخدم / كلمة مرور RPC ل `dcrd` و` dcrwallet` و `dcrctl`.

إذا لم تستخدم `dcrinstall`, سوف تحتاج لتمكين الحد الأدنى من الإعدادات في ملفات التكوين الخاصة بك. متابعة [هذا الدليل](/advanced/manual-cli-install.md#minimum-configuration) لفعل ذلك.

> بداية dcrd 

مع ملفات التكوين الصحيحة, افتح نافذة أخرى وذلك في الدليل الخاص بك Decred (أو استخدام آخر نافذة إذا كنت قد أنشأت محفظتك). أكتب الأمر التالي: (راجع متطلبات هذا الدليل لتحديد الأمر الصحيح لتطبيق OS/Shell الخاص بك):

```no-highlight
dcrd
```

> انتظر مزامن dcrdة إلى سلسلة كتل Decred

عند تشغيل `dcrd` بنجاح, سترى أن نافذة شل ستبدأ بالإمتلاء بالرسائل التي تصل بشكل خفي ثم سيتم البدأ بتجهيز الكل. انتظر حتى تكتمل - سلسلة كتلة ليتم تحميلها في دليل البيانات `dcrd`.

سترى أن سطر البداية كما يلي:

```no-highlight
22:58:04 2016-02-09 [INF] BMGR: Syncing to block height 617 from peer 104.236.167.133:9108
```

لاحقا, سوف تستمر بتحميل الكتل, وسترى أن السطر سيكون كما يلي:

```no-highlight
22:58:16 2016-02-09 [INF] BMGR: Processed 321 blocks in the last 10.03s (544 transactions, height 322, 2016-02-09 09:50:34 +1000 EST)
```

مرة واحدة سيتم من خلالها مزامنة سلسلة الكتلة, أي أحدث ما تم معالجته هو ارتفاع الكتلة الحالي. بحيث يمكنك مقارنة الوقت و التاريخ في سجل الرسائل, أو المقارنة بين إرتفاع الكتلة المعالجة و إرتفاع الكتلة الأخيرة, [المستكشف الكتل الرسمي] (https://mainnet.decred.org/).

لاحظ أن التواثل سوف يستخدم في المستقبل. لذلك يجب عليك ترك مثال `dcrd` من أجل إستخدام وتشغيل` dcrwallet`.

---

الأن يمكنك `dcrd`, يمكنك زيارة دليل [dcrwalletإعدادات] (/getting-started/user-guides/dcrwallet-setup.md).
