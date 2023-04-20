# سيرتي

موقع سيرتي الذاتية.

هذا الموقع بُرمج باستخدام لغة الأسس بشكل كامل (شفرة الخادم وواجهة المستخدم).
* الموقع قائم على البيانات بشكل كامل. كل البيانات الظاهرة في الموقع مخزونة كملفات نصية
  بصيغة ماركداون، بما في ذلك نسخة PDF من السيرة الذاتية.
* الموقع يدعم النمطين الفاتح والداكن.
* بُرمج الموقع باستخدام لغة الأسس ومنصة الويب وتعتمد واجهة المستخدم على تقنية WebAssembly.
* تصميم الموقع متكيف مع عرض الشاشة (responsive web design).
* كُتبت شفرة الموقع باللغة العربية بدل الإنجليزية كمثال على قدرة لغة الأسس على التعامل بعدة
  لغات. يمكن إعادة كتابته بالإنجليزية بشكل كامل. اتصل بي في حال احتجت مساعدة لترجمة الشفرة
  إلى الإنجليزية.

## تخصيص وتشغيل الموقع

لتخصيص الموقع لعرض سيرتك الذاتية:

* استبدل ملفات ماركداون التي في المجلد `الـبيانات` ببياناتك الخاصة.
* عدل عنوان الموقع في ملف `بداية.أسس` بتعديل السطر: `@منفذ_مرئي["/*", "Sarmad Abdullah"]`.
* عرف المتغيرات المحيطية (environment variables) التالية:
  * ‏`SENDGRID_EMAIL`
  * ‏`SENDGRID_API_KEY`
  * ‏`RECAPTCHA_CLIENTKEY`
  * ‏`RECAPTCHA_SERVERKEY`

الآن يمكنك تشغيل الموقع بتنفيذ التالي من سطر الأوامر: `الأسس الشفرة/بداية`. في حال نصبت الأسس
من snapstore فستحتاج لاستخدام الأمر `alusus` بدل `الأسس`.

لنشر الموقع إلى خدمة استضافة:
* عرف المتغيرات المحيطية التالية في حاسوبك الذي تنوي النشر منه:
  * ‏`SEERATY_PUBLISH_USERNAME`
  * ‏`SEERATY_PUBLISH_HOST`
  * ‏`SEERATY_PUBLISH_PORT`
  * ‏`SEERATY_PUBLISH_PATH`
* اضف مفتاح SSH في الخادم الذي ستنشر الموقع فيه.
* عرف المتغيرات المحيطية المذكورة أعلاه على الخادم.
* نصب الأسس على الخادم.
* انشر الموقع باستخدام الأمر: `الأسس الشفرة/بداية انشر`.

الآن سيمكنك تشغيل الموقع على الخادم باستخدام الأمر `الأسس الشفرة/بداية` من الخادم. سيشتغل الموقع
على المنفذ 8000 وكذلك سيشتغل على بروتوكول http وليس https. استخدم خادم ويب مثل Nginx أو Apache
لتحويل الطلبات (عمل proxy) من بروتوكول https ومن المنفذ المطلوب إلى الموقع. 
