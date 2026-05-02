# Level 2 → 3

**🇸🇦 العربية** | [English Below](#english)

---

## الهدف
قراءة ملف اسمه `spaces in this filename`.

## الاتصال
```bash
ssh bandit2@bandit.labs.overthewire.org -p 2220
```

## الحل
```bash
# طريقة 1 — علامات التنصيص
cat "spaces in this filename"

# طريقة 2 — Escape كل مسافة
cat spaces\ in\ this\ filename

# طريقة 3 — Tab Completion (الأسهل)
cat spa<TAB>   # اضغط Tab وبيكمل الاسم لحالو
```

## شو تعلمت؟

هون بديت أفهم كيف الـ Shell بيفسّر الأوامر. لما تكتب `cat spaces in this filename` بدون quotes، الـ Shell بيشوف 4 arguments منفصلين — يعني بيحاول يفتح 4 ملفات مختلفة: `spaces`، `in`، `this`، `filename`. وبالطبع ما في ولا واحد منهم موجود.

الـ Tab Completion اكتشفتها بالصدفة وصارت أحب أداة عندي — مش بس لأنها بتوفر وقت، بس لأنها بتتجنب أخطاء الكتابة كلها.

**الدرس:** فهم كيف الـ Shell بيقسم الأوامر (tokenization) أساسي لكتابة سكريبتات أمنية صحيحة. خطأ واحد بالـ quoting بيسبب ثغرات Command Injection.

---

## English

**Goal:** Read a file named `spaces in this filename`.

**Solution:**
```bash
# Method 1 — Quotes
cat "spaces in this filename"

# Method 2 — Escape each space
cat spaces\ in\ this\ filename

# Method 3 — Tab Completion (easiest)
cat spa<TAB>
```

**What I learned:**

This is where I started understanding how the shell parses commands. When you type `cat spaces in this filename` without quotes, the shell sees 4 separate arguments — it tries to open 4 different files: `spaces`, `in`, `this`, `filename`. None of them exist.

I discovered Tab Completion almost by accident here — and it became my favorite trick. Not just for speed, but because it eliminates typos entirely.

**Real-world note:** Understanding shell tokenization is critical for writing correct security scripts. A single quoting mistake can introduce Command Injection vulnerabilities.

---
*[← Level 1 → 2](level-01-02.md) | [Level 3 → 4](level-03-04.md) →*
