```
╭────────────────────────────────────────────────────────────────────────╮
│                                                                        │
│     ___ ___ ___ _   _ __  __ ___   ___ _   _ ___ _    ___  ___ ___     │
│    | _ \ __/ __| | | |  \/  | __| | _ ) | | |_ _| |  |   \| __| _ \    │
│    |   / _|\__ \ |_| | |\/| | _|  | _ \ |_| || || |__| |) | _||   /    │
│    |_|_\___|___/\___/|_|  |_|___| |___/\___/|___|____|___/|___|_|_\    │
│                                                                        │
│                        ATS-Optimized LaTeX Resumes                     │
│                                                                        │
╰────────────────────────────────────────────────────────────────────────╯
```

<p align="center">
  <b>A conversational Claude prompt that interviews you, drafts what you're unsure how to write,<br>
  and hands back a complete, one-page, ATS-safe LaTeX resume — no LaTeX knowledge required.</b>
</p>

<p align="center">
  <a href="#quick-start">Quick Start</a> ·
  <a href="#whats-inside">What's Inside</a> ·
  <a href="#features">Features</a> ·
  <a href="#preview">Preview</a> ·
  <a href="#faq">FAQ</a>
</p>

---

## What is this?

Most resume templates hand you a wall of `{{PLACEHOLDER}}` text and
leave you to hunt down every field yourself. This is different: it's a
prompt for Claude that **asks you questions first**, one section at a
time, drafts anything you're unsure how to phrase, and only generates
the final document once you've confirmed everything — so what comes
out the other end is *your* resume, not a template with your name
swapped in.

It's built specifically for **fresher and entry-level candidates** —
students and recent graduates who often have strong projects but no
idea how to translate them into resume language, or who are staring
at a blank page wondering where to even start.

## Quick Start

1. Open **[`resume_builder_prompt.md`](templates/resume_builder_prompt.md)**
2. Copy everything inside the code block
3. Paste it into a new chat with Claude
4. Answer the questions as they come — or paste an old resume /
   a project's `README.md` and let Claude pull from that instead
5. Confirm the final recap, and Claude hands you complete,
   ready-to-compile LaTeX
6. Paste it into [Overleaf](https://overleaf.com) (free account),
   hit Compile, download the PDF

No LaTeX installed locally? You don't need it — Overleaf compiles
in the browser.

## What's Inside
| File | What it is |
|---|---|
| [`resume_builder_prompt.md`](templates/resume_builder_prompt.md) | The actual prompt. Paste this into Claude to start. |
| [`trial_resume.tex`](templates/trial_resume.tex) | A fully filled-in example resume (placeholder person) so you can see what the inputs look like. |
| [`trial_resume.pdf`](templates/trial_resume.pdf) | The compiled version of the above — open it directly to see what the final product looks like. |


## Features

**Talks like a person, not a form**
Give it a full sentence and it uses your exact words — it won't
"improve" or rephrase facts you already stated clearly. Give it just
a job title and nothing else, and it drafts a real, specific summary
instead of generic filler like *"results-driven team player"* —
and it actively checks its own draft against a list of AI-sounding
tells (empty triplets, "from X to Y" phrasing, keyword repetition)
before showing it to you.

**Multiple ways to get your project details in**
Type them out, paste an old resume and say *"extract from this,"*
or hand it a project's `README.md` and it pulls the four or five
strongest, most specific bullet points out automatically —
prioritizing real numbers and named tools over generic description.

**Matches a job description without turning into a keyword salad**
Paste a job posting at any point and it re-tunes your summary,
skills order, and project framing around it — weighting "required"
skills over "nice to have" ones, and never claiming a skill you
never actually told it you have. Every reworded sentence still has
to pass the same human-sounding check.

**Actually fits on one page — verified by compiling it, not guessing**
The LaTeX template's font sizing, margins, and spacing were tuned
and checked by real `pdflatex` compilation, including forcing
genuine multi-page overflow to confirm project blocks never get
split across a page break. If your content is borderline, Claude
tells you before generating the file and lets you choose what to
trim, rather than silently cutting content or shrinking fonts
below a readable, ATS-safe size.

**Handles editing and multiple versions**
Once you have a resume, ask for a small fix ("change bullet 3 in
the second project") and only that changes — everything else stays
identical. Ask for a different variant ("now make a cybersecurity
version") and it reframes the same real facts for a different
target role without inventing new skills or projects.

**ATS-safe by construction**
Single column, standard fonts, no tables in the visible content
area, no text below a 10pt floor, selectable PDF text with a
glyph-to-Unicode map so applicant tracking systems parse it cleanly
instead of choking on a fancy template.

## Preview

Want to see the output before committing to the full interview?
Open **[`trial_resume.pdf`](templates/trial_resume.pdf)** — it's a complete,
compiled example built from the same template the prompt generates,
using placeholder data for a fictional candidate.

To compile it yourself: open [Overleaf](https://overleaf.com),
create a new project, upload `trial_resume.tex`, and hit Compile.

## FAQ

**Do I need to know LaTeX?**
No. You never touch the LaTeX directly — you just answer questions
in plain English, and Claude writes the code.

**What if I don't have a polished description of my projects yet?**
Say so. Give Claude whatever raw, unpolished facts you have — even
just a project name and the tech stack — and it drafts realistic
bullets for you to confirm or correct, rather than leaving the
section blank.

**Can I build resumes for more than one target role?**
Yes. Once you have one version done, ask for a variant targeting a
different role and Claude reframes the same real experience around
it, keeping your header, education, and certifications untouched
unless you say otherwise.

**Will it make up experience I don't have?**
No — this is a hard rule throughout the prompt. If a job description
asks for something you never mentioned having, Claude leaves it out
rather than fabricating it.

**What compiler does this expect?**
pdfLaTeX, on A4 paper, 11pt base font. Overleaf's default settings
work out of the box — no manual configuration needed.

---


## 📬 Contact

<div align="center">

[![Email](https://img.shields.io/badge/📧_Email-90dthakur@gmail.com-EA4335?style=for-the-badge)](mailto:90dthakur@gmail.com)
[![LinkedIn](https://img.shields.io/badge/💼_LinkedIn-dev--thakur90-0A66C2?style=for-the-badge)](https://www.linkedin.com/in/dev-thakur90)
[![GitHub](https://img.shields.io/badge/🐙_GitHub-DEVTHAKUR--90-181717?style=for-the-badge)](https://github.com/DEVTHAKUR-90)
[![Portfolio](https://img.shields.io/badge/🌐_Portfolio-devthakur.vercel.app-7C3AED?style=for-the-badge)](https://devthakur.vercel.app)

</div>

<br>

---

## 📄 License

Open source under the [MIT License](LICENSE).

<br>

---

<div align="center">

<br>

⭐ **Star this repo if you found it useful** ⭐

<br>

<img src="https://img.shields.io/badge/Built_with-❤️_by_Dev_Thakur-7C3AED?style=for-the-badge" />

<br><br>

<sub>© 2026 Dev Thakur. All rights reserved.</sub>

</div>
