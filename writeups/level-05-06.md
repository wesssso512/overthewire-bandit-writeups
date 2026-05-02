# Level 5 → 6

**🇸🇦 العربية** | [English Below](#english)

---

## الهدف

إيجاد ملف داخل مجلد inhere (واللي جواه مجلدات كتير) بيطابق 3 شروط:

# أولاً:
قابل للقراءة البشرية.
# ثانياً:
حجمه 1033 بايت بالزبط.
# ثالثاً:
غير قابل للتنفيذ (not executable).

## الاتصال
```bash
ssh bandit5@bandit.labs.overthewire.org -p 2220
```

## الحل
```bash
# استخدام أمر `find` مع الشروط المطلوبة
find ./inhere -type f -readable -size 1033c ! -executable

# بعد ما طلعلي مسار الملف، بطبعه
cat ./inhere/maybehere07/.file2
```

## شو تعلمت؟

هون بلشت أكتشف القوة الحقيقية لأمر `find.` مو بس بقدر أبحث عن اسم، بقدر أفلتر الملفات حسب خصائصها الفيزيائية وحقوق الوصول (Permissions) تبعها. حرف c جنب الحجم بيعني bytes.
**الدرس:**
في مجال الـ `Threat Hunting`، أمر `find` هو السلاح الأساسي لجمع الـ Artifacts. لو كنت عم دور على `Webshell` تم رفعه حديثاً، بقدر أبحث عن ملفات اتعدلت بآخر 24 ساعة ومكتوبة بصيغة معينة، وهالشي بيوفر ساعات من البحث اليدوي.
---

## English

**Goal:** Locate a file hidden somewhere under the `inhere` directory that meets 3 strict conditions:

## First: Human-readable.
## Second: Exactly 1033 bytes in size.
## Third: Not executable.

**Solution:**
```bash
# Use the find command with specific parameters
find ./inhere -type f -readable -size 1033c ! -executable

# Once the path is found, print its contents
cat ./inhere/maybehere07/.file2
```

**What I learned:**

This level showed me the true power of the `find` command. It's not just for searching names; you can filter by physical properties and permissions. The `c` next to the size stands for bytes.
**Real-world note:**
In Threat Hunting or Digital Forensics, `find` is an essential artifact-gathering tool. If I need to locate a recently uploaded webshell, I can search for files modified in the last 24 hours with specific permissions, saving hours of manual digging.
---
*[← Level 4 → 5](level-04-05.md) | [Level 6 → 7](level-06-07.md) →*
