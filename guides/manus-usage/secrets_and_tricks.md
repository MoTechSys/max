# أسرار وحيل Manus AI للمستخدمين المحترفين

هذا الدليل يكشف عن الأسرار والحيل المتقدمة التي يستخدمها المحترفون لتحقيق أقصى استفادة من قدرات Manus AI.

---

### الميزات المخفية أو غير الموثقة

- **سحر `xargs` في `shell`:** يمكنك استخدام `xargs` مع `ls` أو `find` لتطبيق أمر على قائمة من الملفات. على سبيل المثال، لحذف جميع ملفات `.log`:
  ```bash
  find . -name "*.log" -print0 | xargs -0 rm
  ```
- **استخدام `nohup` للمهام الطويلة:** لتشغيل عملية في الخلفية تستمر حتى بعد إغلاق جلسة `shell`، استخدم `nohup`:
  ```bash
  nohup python3 long_running_script.py &
  ```
- **الاستفادة من متغيرات البيئة:** يمكنك تعيين متغيرات بيئة في جلسة `shell` واستخدامها في السكربتات أو أوامرك. هذا مفيد لتخزين القيم المؤقتة أو الأسرار.

---

### حيل يستخدمها المحترفون

- **تسلسل الأوامر الذكي:** استخدم `&&` و `||` لتنفيذ أوامر بشكل مشروط. على سبيل المثال، قم بتثبيت حزمة فقط إذا لم تكن مثبتة بالفعل:
  ```bash
  pip3 show pandas || pip3 install pandas
  ```
- **إعادة توجيه المخرجات المتقدمة:** يمكنك توجيه مخرجات الخطأ `stderr` إلى ملف منفصل لتحليلها لاحقًا:
  ```bash
  python3 my_script.py > output.log 2> error.log
  ```
- **استخدام `grep` مع `regex`:** للبحث عن أنماط معقدة داخل الملفات، استخدم `grep` مع تعبيرات `regex` القوية.

---

### أفضل Skills الجاهزة للتفعيل

يمكنك إنشاء ملفات `bash` script في `/home/ubuntu/skills` لتكون بمثابة "Skills" جاهزة. إليك بعض الأمثلة:

- **`cleanup.sh`:**
  ```bash
  #!/bin/bash
  # حذف الملفات المؤقتة والقديمة
  find /home/ubuntu/Downloads -mtime +7 -delete
  rm -f /home/ubuntu/*.tmp
  ```
- **`backup.sh`:**
  ```bash
  #!/bin/bash
  # نسخ احتياطي لمشروع معين
  tar -czf /home/ubuntu/backups/project_$(date +%F).tar.gz /home/ubuntu/my_project
  ```

---

### إنشاء Skills مخصصة

1.  **أنشئ مجلد `skills`:** `mkdir /home/ubuntu/skills`
2.  **اكتب الـ Skill:** استخدم أداة `file` لإنشاء ملف script جديد، على سبيل المثال `/home/ubuntu/skills/my_skill.sh`.
3.  **اجعله قابلاً للتنفيذ:** `chmod +x /home/ubuntu/skills/my_skill.sh`
4.  **شغل الـ Skill:** `/home/ubuntu/skills/my_skill.sh`

---

### الأوامر المتقدمة

- **`match` مع `grep`:** ابحث عن محتوى معين داخل أنواع ملفات محددة في جميع أنحاء النظام.
- **`file` مع `edit`:** قم بإجراء تعديلات دقيقة ومتعددة على ملفات التكوين أو الكود البرمجي دفعة واحدة.
- **`shell` مع `socat`:** لإنشاء أنفاق TCP أو كشف خدمات الشبكة المحلية للوصول إليها من الخارج.

---

### جعل Manus يتذكر التفضيلات

يمكنك إنشاء ملف `.manus_profile` في `/home/ubuntu` لتخزين التفضيلات والإعدادات المخصصة. سيقوم Manus بتحميل هذا الملف في بداية كل جلسة `shell`.

**مثال على `.manus_profile`:**
```bash
# Aliases
alias ll=\'ls -alF\'
alias update=\'sudo apt-get update && sudo apt-get upgrade -y\'

# Environment Variables
export MY_API_KEY=\'your_secret_key\'
```
