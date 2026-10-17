# m01l01-05 · Reading the four steps in a real auth.log

**Lesson:** [CIA Triad, Non-Repudiation & Parkerian Hexad](https://learnsome.tech/learn/cybersecurity-course/m01l01) (lesson 1.1, module 1: Core Security Principles) · Free  
**Check:** Graded

## Goal

You can name which security property an incident broke, show why a shared key cannot give non-repudiation while a signature can, and trace identification, authentication, authorisation and accountability through a real auth.log.

## Files

- [`starter/auth.log`](starter/auth.log)
- [`starter/iaaa.py`](starter/iaaa.py): the listing from the lesson
- [`expected.txt`](expected.txt): the output the check compares with
- [`check.json`](check.json): how `./check` runs and checks this lab

## Steps

1. Go to the starter: `cd labs/m01l01/m01l01-05/starter`
2. Read `iaaa.py` the way the lesson builds it:
   - Lines 1–6: Two regular expressions
   - Lines 7: marked as shared
   - Lines 8–20: walks the file
3. Run it: `python3 iaaa.py`.
4. Check it from the repository root: `./check m01l01-05`.

## Expected output

```text
09:12:41 admin   authn failed password from 198.51.100.23
09:13:05 alice   authn accepted publickey from 203.0.113.7
09:14:02 alice   authz allowed as root: /usr/bin/systemctl restart nginx
09:14:30 bob     authn accepted publickey from 203.0.113.9
09:15:10 bob     authz refused as root: /usr/bin/cat /etc/shadow
09:16:44 deploy? authn accepted password from 203.0.113.50
09:17:20 deploy? authz allowed as root: /usr/bin/rm -rf /srv/app/releases
```

## How to check

`./check m01l01-05` copies `starter/` into a scratch directory and runs `python3 iaaa.py` there, the way the site's lab sandbox does: that directory is the working directory and `HOME`, `LANG=C.UTF-8`, `TZ=UTC`, a limit of 10 seconds and 256 KiB of output per stream.

It passes when the output matches `expected.txt` by the site's rules, within the limits. Standard output is compared line by line; spaces at the end of a line and blank lines at the end do not count. If that differs, standard output followed by standard error is compared with Python traceback frames and blank lines set aside, so a lesson that shows an error passes when your program prints the same error. A pass here is a pass on the site.

---

[Open the lesson on LearnSome.tech](https://learnsome.tech/learn/cybersecurity-course/m01l01) · [All labs of this lesson](../README.md) · [Course README](../../../README.md)
