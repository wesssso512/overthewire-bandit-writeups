# Level 4 → 5

**🇸🇦 العربية** | [English Below](#english)

---

## الهدف
العثور على الملف الوحيد القابل للقراءة البشرية (human-readable) داخل مجلد `inhere` واللي بيحتوي على مجموعة من الملفات.
## الاتصال
```bash
ssh bandit4@bandit.labs.overthewire.org -p 2220
```

## الحل
```bash
# الدخول للمجلد
cd inhere

# فحص نوع كل الملفات الموجودة
file ./*

# بعد ما اكتشفت إنو -file07 هو النصي
cat ./-file07
```

## شو تعلمت؟

اللينكس ما بيهتم بصيغة الملف (Extensions) مثل الويندوز (يعني ما بيهمه إذا الملف آخره `.txt` أو `.exe`). أمر file بيقرأ الـ `"Magic Bytes"` تبع الملف من جوا وبيحكيلك شو نوعه الحقيقي.

**الدرس:**
بالهندسة العكسية أو تحليل البرمجيات الخبيثة، المهاجم ممكن يسمي الفايروس image.jpg. أمر file بيكشف الخدعة فوراً وبيقلي إنو هاد بالأساس ملف تنفيذي (Executable) مو صورة.

---

## English

**Goal:** Find the only human-readable file among several files inside the `inhere` directory.

**Solution:**
```bash
# Enter the directory
cd inhere

# Check the file type of all items inside
file ./*

# Once identified that -file07 is ASCII text
cat ./-file07
```

**What I learned:**

Linux doesn't care about file extensions the way Windows does (a file doesn't need to end in `.txt` to be text). The file command reads the internal `"Magic Bytes"` of a file to tell you its true format.

**Real-world note:**
In malware analysis or incident response, an attacker might rename an executable to `image.jpg` to bypass filters. The file command immediately calls out the bluff, revealing the true nature of the file.

---
*[← Level 3 → 4](level-03-04.md) | [Level 5 → 6](level-05-06.md) →*
