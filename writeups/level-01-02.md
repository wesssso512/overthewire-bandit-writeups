# Level 1 → 2

**🇸🇦 العربية** | [English Below](#english)

---

## الهدف
قراءة ملف اسمه `-` (شرطة).

## الاتصال
```bash
ssh bandit1@bandit.labs.overthewire.org -p 2220
```

## الحل
```bash
cat ./-
```

## شو تعلمت؟

هاد أول مستوى وقفت فيه فعلاً. كتبت `cat -` وما صار شيء — الـ terminal ضل يستنى. جربت مرات. ما فهمت ليش.

المشكلة: الـ `-` بـ Linux ما هو ملف عادي من وجهة نظر الـ Shell — هو رمز خاص يعني "اقرأ من الـ stdin" (المدخلات المباشرة). يعني `cat -` قاله "استنى مني أكتبلك شيء"، مش "افتح الملف المسمى شرطة".

الحل هو إنك تعطيه المسار الكامل `./-` — هيك بتقول للـ Shell صراحةً "هاد ملف موجود هون" مش رمز.

**الدرس:** في الـ Penetration Testing كثيراً بتشوف ملفات بأسماء غريبة أو أحرف خاصة — المهاجمون أحياناً بسموا ملفاتهم هيك عن قصد عشان يعطلوا أدوات التحليل.

---

## English

**Goal:** Read a file named `-` (a dash).

**Solution:**
```bash
cat ./-
```

**What I learned:**

This is where I actually got stuck for the first time. I typed `cat -` and nothing happened — the terminal just waited. Tried again. Still nothing.

The issue: `-` in Linux is a special symbol meaning "read from stdin." So `cat -` told the shell "wait for me to type something," not "open the file named dash."

The fix is giving the full path `./-` — explicitly telling the shell "this is a file right here," not a symbol.

**Real-world note:** Attackers sometimes name their files or scripts with special characters to confuse log parsers and analysis tools. Knowing how the shell interprets special characters matters.

---
*[← Level 0 → 1](level-00-01.md) | [Level 2 → 3](level-02-03.md) →*
