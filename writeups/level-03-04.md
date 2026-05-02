# Level 3 → 4

**🇸🇦 العربية** | [English Below](#english)

---

## الهدف
قراءة محتوى الملف المخفي داخل مجلد `inhere`.

## الاتصال
```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
```

## الحل
```bash
# طريقة 1 — ls مع -a لإظهار المخفي
cd inhere
ls -a
cat .hidden

# طريقة 2 — مباشرة
cat inhere/.hidden

```

## شو تعلمت؟

بالبداية لما دخلت المجلد وكتبت `ls` لحالها، فكرت المجلد فاضي. هون اتعلمت إنو بنظام لينكس، أي ملف بيبدأ بنقطة `.` بيكون مخفي عن العرض العادي. استخدام الـ flag `-a` مع أمر `ls` بيعرض كل شيء. 

**الدرس:**
من وقتها وللآن، مستحيل اعتمد على العرض الافتراضي. المهاجمين دايماً بيخفوا ملفاتهم الخبيثة (Malware) أو أدواتهم باستخدام نقطة ببداية الاسم، لذلك `ls -la` هو أول أمر لازم أكتبه لما أستكشف أي مسار.

---

## English

**Goal:** Read the password hidden in a file within the inhere directory.

**Solution:**
```bash
# Go into the directory
cd inhere

# List all files, including hidden ones
ls -la

# Read the hidden file
cat .hidden
```

**What I learned:**

At first, when I entered the directory and typed `ls`, it looked empty. I learned that in Linux, any file starting with a dot `.` is hidden from normal view. Using the `-a` flag with `ls` forces it to show everything.

**Real-world note:** 
From now on, I can never rely on default views. Attackers constantly hide malicious scripts or payloads by simply prefixing the filename with a dot. Running `ls -la` is muscle memory now when enumerating directories.

---
*[← Level 2 → 3](level-02-03.md) | [Level 4 → 5](level-04-05.md) →*
