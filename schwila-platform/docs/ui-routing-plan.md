# 🧭 خطة تنفيذ مسارات واجهة منصة السكويلة (Next.js)

## 🎯 الهدف
إنشاء بنية صفحات واضحة لتجربة تعلّم منظمة، متدرجة، وسهلة التوسعة عبر Next.js.

---

## 🧱 مسارات الواجهة الأساسية

| المسار                      | الوظيفة                                               |
|-----------------------------|--------------------------------------------------------|
| `/`                         | الصفحة الرئيسية (مقدمة + دعوة للدخول إلى المسارات)    |
| `/tracks`                   | عرض المسارات التعليمية (مبتدئ، متوسط، متقدم...)       |
| `/tracks/[track]`           | عرض وحدات المستوى المحدد (مثل Beginner)               |
| `/tracks/[track]/[module]`  | عرض درس أو وحدة محددة من Markdown                     |
| `/about`                    | تعريف بالمنصة، الرؤية، الفريق                         |
| `/docs`                     | عرض الوثائق التقنية للمشروع (للمساهمين والمطورين)     |

---

## 🧩 الخطوات التقنية المقترحة

1. **تهيئة مشروع Next.js**
   - استخدام `Tailwind CSS` للأنماط
   - دعم قراءة ملفات Markdown من `content/`

2. **إنشاء الصفحات التالية:**
   - `src/pages/index.tsx`
   - `src/pages/tracks/index.tsx`
   - `src/pages/tracks/[track]/index.tsx`
   - `src/pages/tracks/[track]/[module].tsx`
   - `src/pages/about.tsx`
   - `src/pages/docs.tsx`

3. **بناء مكونات قابلة لإعادة الاستخدام:**
   - رأس الصفحة (`Header`)
   - الشريط الجانبي للمسارات (`Sidebar`)
   - مكوّن عرض الدرس (`LessonViewer`)
   - شريط التقدم (`ProgressBar`)

4. **الربط مع ملفات Markdown:**
   - تحديد صيغ الحقول في ملفات `.md` مثل:
     ```yaml
     ---
     title: "مقدمة إلى البرمجة"
     duration: "10 دقائق"
     slug: "module-01-intro"
     track: "beginner"
     ---
     ```

5. **التوسعة المستقبلية:**
   - إضافة Auth للمستخدمين
   - تتبّع التقدم (localStorage ← لاحقًا DB)
   - مساعد ذكي في كل صفحة

---

## 🧑‍💻 حالة التنفيذ (متابعة التقدّم)

- [ ] تهيئة مشروع Next.js + Tailwind  
- [ ] إنشاء صفحة `/tracks`  
- [ ] ربط `/tracks/beginner` بمحتوى `content/level-beginner/`  
- [ ] بناء مكوّن `LessonViewer`  
- [ ] عرض أول درس من Markdown  
- [ ] ربط التنقل بين الدروس

---

## 📦 الملفات ذات الصلة

- `src/pages/tracks/`
- `src/components/`
- `content/level-beginner/*.md`
- `docs/ui-routing-plan.md`
