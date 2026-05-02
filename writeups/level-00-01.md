# Level 0 → 1

**🇸🇦 العربية** | [English Below](#english)

---

## الهدف
الاتصال بالسيرفر عبر SSH وقراءة الباسورد من ملف اسمه `readme`.

## الاتصال
```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
# password: bandit0
```

## الحل
```bash
ls
cat readme
```

## شو تعلمت؟

هاد المستوى بسيط — بس كان أول مرة أتصل بسيرفر Linux عن بُعد بحياتي بطريقة "أمنية". قبل هيك كنت أعرف SSH كمفهوم من الكورسات، بس لما كتبت الأمر أول مرة وشفت الـ terminal يتصل بسيرفر ثاني، حسيت إنها قوة حقيقية.

الـ `cat` أمر تافه — بس اللي مهم هون إنك فهمت إن كل شيء بـ Linux هو ملف، والوصول للملف = الوصول للمعلومة.

**الدرس:**
 في الأمن السيبراني، أول خطوة دايماً هي الوصول — وSSH هو أكثر بروتوكول منتشر للوصول للسيرفرات.

---

## English

**Goal:** Connect via SSH and read the password from a file named `readme`.

**Connection:**
```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
# password: bandit0
```

**Solution:**
```bash
ls
cat readme
```

**What I learned:**

Simple level — but it was my first real SSH connection to a remote server. I knew SSH from courses theoretically, but actually typing the command and seeing the terminal connect to another machine felt different. Real.

The `cat` command is trivial. What matters is understanding that in Linux, **everything is a file**, and accessing the file = accessing the information.

**Real-world note:** SSH is the most common protocol for remote server access. In penetration testing, finding an exposed SSH port is often the first step toward compromise.

---
*[← Back to README](../README.md) | [Level 1 → 2](level-01-02.md) →*
