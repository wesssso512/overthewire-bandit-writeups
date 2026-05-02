# Level 6 → 7

**🇸🇦 العربية** | [English Below](#english)

---

## الهدف
البحث في كامل السيرفر عن ملف بيملكه المستخدم bandit7 والمجموعة bandit6 وحجمه 33 بايت.
## الاتصال
```bash
ssh bandit6@bandit.labs.overthewire.org -p 2220
```

## الحل
```bash
# البحث من الجذر (/) مع إخفاء رسائل الخطأ
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null

# طباعة الملف الناتج
cat /var/lib/dpkg/info/bandit7.password
```

## شو تعلمت؟

البحث بكامل السيرفر `/` بيطلع شاشة مليانة رسائل `"Permission denied"` لأنو ما عندي صلاحيات أدخل كل المجلدات. هون تعلمت خدعة تحويل الأخطاء `(stderr)` للعدم باستخدام `2>/dev/null`. هاد بيخلي الشاشة نظيفة وبيطلعلي بس النتيجة الصح.

**الدرس:**
هذي المهارة حيوية جداً في مرحلة تصعيد الصلاحيات (Privilege Escalation). لما أعمل `Enumeration` على سيرفر مخترق، بحتاج ألاقي ملفات بيمتلكها الـ `Root` وفيها صلاحيات خاطئة `(SUID)`، وإخفاء الأخطاء بيخليني أركز على الثغرات بدون ما أضيع بالرسائل المزعجة.

---

## English

**Goal:** Search the entire server for a file owned by user *bandit7*, group *bandit6*, and exactly *33* bytes in size.

**Solution:**
```bash
# Search from root (/), redirecting errors to null
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null

# Read the found file
cat /var/lib/dpkg/info/bandit7.password
```

**What I learned:**

Searching the entire server `/` generates a flood of `"Permission denied"` errors because I don't have access to everything. I learned the trick of redirecting standard error `(stderr)` to the void using `2>/dev/null`. This keeps the terminal clean and only shows the successful hits.
**Real-world note:**
This is a core technique for Linux Privilege Escalation. When enumerating a compromised box, I often search for misconfigured files (like `SUID` binaries) owned by `root`. Redirecting errors ensures I don't miss the actual vulnerability hidden in the noise.

---
*[← Level 5 → 6](level-05-06.md) | [Level 7 → 8](level-07-08.md) →*
