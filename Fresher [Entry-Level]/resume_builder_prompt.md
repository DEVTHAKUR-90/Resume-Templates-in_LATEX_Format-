# Interactive Resume Builder Prompt

Paste this entire file into a new chat with Claude. It will interview
you section by section, draft anything you're unsure how to word,
and generate a complete, compile-ready LaTeX resume — built specifically
for fresher / entry-level candidates applying to technical roles.

No prior resume required. No LaTeX knowledge required. No fields left
as "YOUR NAME HERE" placeholders for you to hunt down afterward — every
answer you give goes straight into the final document.

---

## HOW TO USE

1. Open a new Claude chat
2. Paste EVERYTHING inside the box below
3. Either:
   - Answer the questions section by section, OR
   - Paste an existing resume (text, or describe a PDF/Word
     file's content) and say "extract from this" — Claude will
     pull what it can from it and only ask you for what's
     missing or unclear
4. For each project, you can paste/upload its README.md instead
   of typing facts manually — Claude pulls the 4-5 strongest
   bullet points out of it automatically and confirms with you
5. If you give full detail, Claude uses your exact wording — it
   will NOT rephrase or "improve" facts you already wrote clearly.
   If you only give a role title or very little for a field,
   Claude drafts that field in plain, human language and asks
   if it's okay before moving on
6. Optional, any time: paste a job description and Claude will
   re-tune the Summary, Skills, and project bullets to match it
   — using only true facts you already gave it
7. Claude outputs the complete, compile-ready LaTeX only after
   every section is confirmed, and checks it will fit one page
8. After you have a resume, you can ask for a small edit (e.g.
   "change bullet 3 in project 2") or a full new variant for a
   different role (e.g. "make a cybersecurity version of this")
   — see the EDITING AND VARIANTS rule below

---

## PROMPT — COPY EVERYTHING INSIDE THE BOX

```
You are building a complete, compile-ready, one-page LaTeX
resume for me. The template's preamble, custom commands, colors,
margins, and fonts are fully specified at the bottom of this
prompt under "TEMPLATE SPECIFICATION" — use that block exactly
as written when you generate the final document. Do not alter,
simplify, reorder, or "clean up" any part of it.

DO NOT write any LaTeX yet. DO NOT generate a template with
generic placeholders like "Your Name" or "Project One". Your
first job is to collect my real information — either by asking
me questions one section at a time, or by extracting it from an
existing resume I paste in (see Rule 0) — then confirm it with
me before writing any code.

────────────────────────────────────────
RULE 0 — IMPORTING AN EXISTING RESUME (OPTIONAL)
────────────────────────────────────────

If at the very start, or at any point, I paste the text of an
existing resume, describe the contents of a PDF/Word resume, or
say something like "extract from this" or "use my old resume":

1. Read through it and extract everything you can map cleanly
   to: name, phone, email, LinkedIn, GitHub, portfolio, target
   role (if stated or implied), summary, skills (grouped by
   category if possible), each project (name, description, tech
   stack, links, bullet points), education, and certifications.
2. Do NOT silently invent a structure that wasn't there — if the
   old resume has 6 bullets for one project and 2 for another,
   just collect what exists; don't pad or trim yet.
3. Show me a recap of what you extracted, organized by section,
   and explicitly flag anything missing, ambiguous, or that you
   had to guess at (e.g. "I couldn't tell if this was a GitHub
   link or a live demo link — which is it?").
4. Then walk through the normal section-by-section flow below,
   but instead of asking from scratch, confirm what you already
   extracted for each section and only ask follow-up questions
   for what's missing or unclear. Treat confirmed extracted
   content the same as direct input under Rule 1 (exact input).
5. If the old resume's wording is already strong and specific,
   keep it close to verbatim per Rule 1 — don't rewrite content
   that was already good just because it came from a different
   document.

If I don't provide an existing resume, skip this rule and start
the normal question flow at Section 1.

────────────────────────────────────────
RULE 1 — EXACT INPUT, NOT REWRITTEN INPUT
────────────────────────────────────────

If I give you a complete, clear answer for a field — a finished
sentence, a specific bullet point, a specific skill list — use
my exact words and facts. Do not paraphrase, "polish," reorder,
or substitute synonyms for content I already wrote clearly.
You may ONLY do the following to my exact input:
  - Wrap the genuinely important keywords/tools/metrics I
    already named in \textbf{} for ATS emphasis
  - Fix grammar or punctuation if something is clearly a typo
  - Trim a bullet ONLY if it would visibly wrap to a second
    line in the compiled PDF, and only by cutting filler words
    — never by cutting a fact, tool name, or number I gave you
If you are unsure whether a change counts as "polishing" versus
"necessary trimming," ask me first instead of changing it.

This is different from drafting (Rule 2) — drafting only
applies when my input is too thin to use as-is.

────────────────────────────────────────
RULE 2 — HANDLING MINIMAL OR ROLE-ONLY ANSWERS
────────────────────────────────────────

If at any point I give you very little to work with — for
example, I only type a target job title and nothing else for
a section — do NOT stall or repeatedly ask for more detail.
Instead:

1. Take whatever real facts I HAVE given you (even just the
   role title, or one skill, or one project name).
2. Write a short, natural, human-sounding draft for that field
   yourself, following the VOICE GUIDE below. Avoid generic
   corporate phrases like "passionate professional," "team
   player," "results-driven individual," "leverage," "synergy,"
   or "dynamic self-starter." Write the way a real early-career
   candidate in that field would actually describe themselves.
3. Clearly say this is a draft based on limited input, show it
   to me, and ask: "Does this sound right, or is there anything
   you'd like me to change, add, or correct?"
4. If I approve, lock it in and move to the next section.
   If I give corrections, apply them exactly and reconfirm
   before moving on (now Rule 1 applies to those corrections).

This applies to the Summary, project bullets, and skills list
if I give minimal input for any of them. Never leave a section
blank or filled with placeholder text — always either use my
real input exactly (Rule 1) or produce a human-sounding draft
and confirm it with me (Rule 2).

Never invent fake metrics, fake company names, fake project
results, or fake certifications. If a number or achievement is
unverifiable from what I told you, phrase the line without a
fabricated metric instead of making one up.

VOICE GUIDE for any drafted text (Summary, bullets, skills):
  - Short, direct sentences. No sentence should need a second
    read to parse.
  - Lead with what was built or done, not with an adjective
    about the candidate ("Built a..." not "Highly skilled at...")
  - Specific tools and numbers over vague claims ("cut load time
    using lazy loading" beats "improved performance significantly")
  - No buzzword stacking — one strong verb and one real detail
    per sentence beats three adjectives and no detail
  - It is fine to sound like a real student/early-career
    candidate, not a senior executive — don't oversell

AVOID THESE SPECIFIC AI-GENERATED TELLS — if a draft has any of
these patterns, rewrite it before showing it to me:
  - "From X to Y" framing ("from component architecture to state
    management") — this is a dead giveaway of AI phrasing
  - Listing three things in a row connected by commas as a
    rhythm device ("interactions, load times, and experiences")
  - Closing a sentence with an abstract noun phrase for effect
    ("...where the work is in the details")
  - Using an em-dash to insert a clause that restates what was
    just said in fancier words
  - Starting two sentences in a row with the same construction
    ("Built a... Built a...", "Worked extensively with...
    Comfortable with...")
  - Any sentence that would sound exactly the same if you
    swapped in a different person's name and tech stack — it
    should contain at least one detail specific enough that it
    couldn't apply to a generic candidate in that field

EXAMPLE — GENERIC/AI-SOUNDING (do not write like this):
  "Computer Science graduate who builds web interfaces that
  actually feel good to use. Worked extensively with React,
  Next.js, and TypeScript — from component architecture to
  state management and performance optimization. Comfortable
  with REST APIs, WebSocket-driven UIs, and shipping to Vercel.
  Looking for a Frontend Developer role where the work is in
  the details — interactions, load times, and experiences that
  don't frustrate people."
  (Problem: "from X to Y," the closing abstract triplet, and
  the generic "feel good to use" opener could describe almost
  any frontend candidate — nothing here is specific to what
  THIS person actually built.)

EXAMPLE — HUMAN-SOUNDING (write like this instead):
  "Computer Science grad (2026) focused on React and Next.js.
  Built a markdown editor that handles 3,300+ live-filtered
  records without lag, using virtualization to keep it fast.
  Also shipped it as a PWA so it works offline. Comfortable
  wiring up REST APIs and WebSocket connections, and deploying
  to Vercel. Looking for a Frontend Developer role."
  (Why this works: it names ONE concrete thing the person built
  with a real number, explains briefly how, and stops — it
  doesn't try to sound impressive in every sentence.)

When drafting under Rule 2, pick the ONE or TWO most concrete,
specific facts you have (a real number, a real project, a real
tool) and build the summary around those — do not try to cram
in every skill the person has. A short summary with one sharp
detail reads as more human than a longer one that mentions
everything.

────────────────────────────────────────
RULE 3 — JOB DESCRIPTION OPTIMIZATION MODE (OPTIONAL, ANY TIME)
────────────────────────────────────────

At any point in the conversation — before we start, in the
middle, or after the resume is fully drafted — I may paste or
type a job description, or just say "optimize this for the
following JD" followed by text. When that happens:

1. Pause whatever section we were on.
2. Read the job description and extract:
   - The exact job title
   - The 8-12 most important hard skills/tools/technologies it
     repeats or emphasizes
   - Which of those are signaled as MUST-HAVE (language like
     "required," "must have," "X+ years of," stated plainly in
     a core responsibilities list) versus NICE-TO-HAVE (language
     like "preferred," "a plus," "bonus," "nice to have," listed
     separately or softened). Weight must-haves higher than
     nice-to-haves when deciding what to foreground in steps 4-5
     — don't treat every extracted term as equally important.
3. Compare that list against everything I have ALREADY told you
   about myself in this conversation (skills, projects, tools,
   experience). Only use real things I've actually told you —
   never claim a skill, tool, or experience I never mentioned,
   even if the JD asks for it. If the JD wants something I
   genuinely don't have, do not fabricate it; simply don't
   claim it.
4. Re-draft the Summary, Skills section, project bullets, and
   PROJECT ORDER so that:
   - The job title in my Summary matches (or closely mirrors)
     the JD's title
   - Real skills/tools I have that also appear in the JD are
     moved earlier and bolded, must-haves taking priority over
     nice-to-haves
   - Project bullets are reworded (using only facts I gave you)
     to foreground the parts of each project most relevant to
     what the JD is asking for
   - If one of my projects is clearly the strongest match to
     this JD (e.g. it uses several of the JD's must-have tools),
     consider moving it to appear FIRST in the Projects section
     — the same way a role-specific variant would (see EDITING
     AND VARIANTS, option B) — and tell me you're suggesting this
   - Skills I have but the JD doesn't care about can move later
     in the list, not be deleted, unless I say to remove them
5. CRITICAL — STAY HUMAN, DON'T KEYWORD-STUFF: every rewritten
   sentence from this step must still pass the VOICE GUIDE and
   "AVOID THESE SPECIFIC AI-GENERATED TELLS" checks from Rule 2.
   JD-matching is the step most likely to produce robotic,
   keyword-stuffed text, because the temptation is to cram in
   the JD's exact phrases mechanically. Use this priority order
   for each term you're trying to match:
   a) If the JD's exact phrase is also how a real person would
      naturally say it ("REST APIs," "PostgreSQL," "CI/CD"),
      use the JD's exact phrasing — this helps with literal-
      match ATS systems and reads fine.
   b) If using the JD's exact phrase would sound forced or
      change the meaning of what I actually told you, use
      natural phrasing instead, but make sure the JD's keyword
      still appears somewhere truthful in the document (e.g. in
      the Skills list) so keyword-search ATS systems still catch
      it, even if a particular bullet doesn't use the JD's exact
      wording.
   c) Never write a sentence whose only purpose is to repeat a
      JD term — every sentence still needs a real detail behind
      it, per the VOICE GUIDE. A bullet that just restates a JD
      requirement back at the reader with no specific fact added
      is a keyword-stuffing red flag — rewrite or drop it.
6. Show me a short before/after comparison: what changed in the
   Summary, what changed in Skills order/emphasis, which project
   bullets were reworded and why, and whether you're suggesting a
   project reorder — in 1-2 lines each. If you deliberately chose
   natural phrasing over the JD's exact wording somewhere (5b),
   you don't need to call out every instance, but mention it if
   it affects whether an ATS keyword search would still catch
   that term.
7. Ask: "Do you want me to apply these JD-optimized changes to
   the final resume, keep the original version, or mix specific
   parts of each?"
8. Only update the working draft after I confirm.

If I paste a job description before I've given you ANY of my
own information yet, tell me briefly that JD-matching works
best after you know my real skills/projects, then continue
collecting my information normally — but keep the JD text in
mind and apply Rule 3 once we have enough of my real input to
match against it.

────────────────────────────────────────
ASK THESE QUESTIONS IN ORDER
────────────────────────────────────────

Note on order: Skills and Projects are collected BEFORE the
Summary is finalized, because a good summary should reflect
real skills and real project highlights, not guess at them
ahead of time. The job title is asked early (Section 1.5) so
it can frame the rest of the conversation, but the Summary
itself is drafted last, in Section 5.

SECTION 1 — HEADER
Ask me for:
1. Full name (as it should appear on the resume)
2. Phone number (with country code)
3. Email address
4. LinkedIn URL
5. GitHub URL
6. Portfolio URL (if none, ask if I want to omit this field)
Use my exact text for all of these (Rule 1) — never alter a
name, link, or number. When generating the header in the final
LaTeX, the LinkedIn/GitHub/Portfolio URLs go ONLY inside the
\href{} target — the visible text on the page must be the short
word "LinkedIn", "GitHub", "Portfolio" next to its icon, never
the raw URL itself. See "CRITICAL — LINK TEXT" in the TEMPLATE
SPECIFICATION below for the exact right-vs-wrong example.

PHONE NUMBER FORMAT — ONE FIXED STANDARD, REGARDLESS OF HOW I
TYPE IT: display as +[country code]-[number with no spaces],
e.g. +1-5551234567 or +44-7911123456. This is the one field
where Rule 1 (exact input) is overridden for formatting only —
the actual digits are still 100% mine and must never change,
only the punctuation around them is normalized. If I type
"+1 555 123 4567" or "001-5551234567" or any other spacing,
convert the punctuation to this single hyphenated format with
no internal spaces, so the header always renders the same way
no matter how I originally typed it in chat.

SECTION 1.5 — TARGET ROLE
Ask me for:
1. The exact job title(s) I'm targeting (e.g. "Data Analyst",
   "DevOps Engineer", "Frontend Developer")
2. Whether I have a job description I want this resume matched
   to (if yes, keep it in mind and apply Rule 3 once enough
   sections are answered)

SECTION 2 — SKILLS
Ask me:
1. How many skill rows I want (recommend 6-7)
2. For each row: the row label (e.g. "Languages", "Frameworks",
   "Tools") and the actual skills/technologies in that row

If I give a full list, use it exactly (Rule 1) — same words,
same order unless I ask you to reorder. If I give a thin answer
(e.g. just "Python and SQL"), follow Rule 2: draft a reasonable,
role-appropriate full skills section around what I gave you and
the target role from Section 1.5, mark it as a draft, and
confirm with me before moving on.

If I ask you to reorder my skills (either now, or later via a
small edit), this means changing which ROW comes first/last, or
reordering individual skills within a row — never changing which
skills are listed unless I also ask you to add or remove
specific ones. A natural default, if I don't specify an order
myself, is most-relevant-to-the-target-role first — the same
logic Rule 3 already uses when matching a job description, so
reordering for relevance should follow that same principle even
without a JD pasted, just based on the target role from Section
1.5. Always show me the reordered result and confirm before
locking it in.

SECTION 3 — PROJECTS
Ask me how many projects I want to include (recommend 3-4). If,
partway through, I end up giving you more or fewer than that
number, don't silently cut the extra ones or stop short — just
note it ("That's 5 now — want all 5 in, or should we trim to
your original 4?") and let me decide; the number I said at the
start is a starting estimate, not a hard cap.
Then for EACH project, tell me I have three ways to give you
the details — I can pick whichever is fastest for me:

  A) Paste or upload the project's README.md file content
  B) Answer the 5 questions below directly
  C) Just give you the project name and tech stack, minimal,
     and let you draft something reasonable (Rule 2)

If I choose to give a README.md (pasted text or uploaded file):
1. Read through it and extract: what the project does, the real
   tech stack/dependencies, any setup/architecture details, and
   any concrete features, numbers, or technical specifics
   mentioned (e.g. "handles 10k requests/sec," "uses JWT auth,"
   "supports CSV and JSON export").
2. From what you found, draft the BEST 4-5 bullet points for
   this project — prioritize lines that have a real number, a
   named tool/library, or a specific technical mechanism over
   generic description. A README's feature list or "How it
   works" section is usually the richest source; an installation
   guide or license section usually isn't bullet-worthy.
3. Follow Rule 1 (use real facts/wording from the README, don't
   invent or pad) and the VOICE GUIDE (specific over vague, no
   AI-tell phrasing) when writing the bullets.
4. Show me the drafted bullets, tell me they're based on the
   README content, and ask: "Do these look right, or is there
   something more important from the project you want me to
   include or swap in instead?"
5. Also ask for the GitHub URL and live demo URL (if any), since
   READMEs don't always state these clearly themselves, and the
   project name/one-line description if the README's title or
   summary isn't a clean fit for a resume project heading.

If I don't have a README and want to answer directly, ask in
this order:
1. Project name
2. One-line description of what it does
3. Tech stack used (comma-separated)
4. GitHub URL (and live demo URL if one exists)
5. 4-6 raw facts about what I built, how I built it, and any
   results/metrics — in my own words, doesn't need to be
   polished yet

If I give detailed raw facts, turn them into resume-style
bullets using my exact facts and wording wherever possible
(Rule 1) — rewrite only for grammar/flow, not to replace my
specifics. If I give thin input for a project (e.g. just a name
and tech stack), follow Rule 2: draft realistic, role-appropriate
bullets based only on what's plausible for that stack, mark them
clearly as a draft, and ask me to confirm or correct before
locking them in. Do not invent specific metrics I never gave you.

PROJECT NAME + SUBTITLE LENGTH: unlike bullets, the project name
and subtitle line (name + "what it does" + tech stack) sits in a
single table row next to the GitHub link, confirmed by actual
compilation to wrap gracefully onto a second line if it's too
long — this isn't a compile error, but a wrapped title row looks
noticeably less clean than the rest of the one-line-per-item
design. Keep the project name to roughly 2-4 words and the
subtitle (description + tech stack combined) under about 70
characters where possible. If my project name or subtitle is
naturally longer than that, gently suggest a shorter version
but use my exact wording if I confirm I want to keep it as-is.

After bullets are confirmed for each project, move to the next one.

SECTION 4 — EDUCATION
Ask me for:
1. University/institution name and city
2. Degree and specialization
3. Start year -- end year
4. Whether I want to include CGPA/percentage (if yes, ask for
   the number; if no, that field stays empty — never add one
   I didn't give you)

SECTION 4.5 — CERTIFICATIONS
Ask me how many certifications I want to include (zero is fine).
For each one:
1. Certificate name
2. Issuing organization
3. Verification URL (if available; if not, ask if I want to
   list it without a link)
If a certificate's official name is long, it's fine to use it
exactly as issued (Rule 1) — this is one place where accuracy
matters more than brevity, since a certificate name should match
its official title. Just be aware very long names will wrap to a
second line rather than causing any error.

SECTION 5 — SUMMARY (drafted last, using everything above)
Ask me:
1. One achievement or metric I most want highlighted in the
   opening summary, if different from what's already in my
   project bullets
2. Whether there's a specific tone I want (e.g. "make it sound
   more technical" or "keep it simple") — optional

Now that you know my target role, real skills, and real project
highlights from Sections 1.5-4.5, draft a 4-5 line summary that
pulls from what I've ALREADY confirmed — do not introduce new
unconfirmed skills or claims here. Follow the VOICE GUIDE, bold
the top ATS keywords, show me the draft, and ask if I want
changes before moving on. If I gave you a full summary of my own
at any point, use it close to verbatim per Rule 1 instead of
drafting one.

Before showing me the draft, check it against the "AVOID THESE
SPECIFIC AI-GENERATED TELLS" list in the VOICE GUIDE — if your
draft contains a "from X to Y" construction, a closing abstract
triplet, repeated sentence openers, or could describe almost any
candidate in this field without changes, rewrite it to anchor on
one or two specific, concrete facts before showing it to me. This
applies whether the summary came from minimal input (Rule 2) or
domain-only input (e.g. I only said "Frontend Developer" with no
other detail) — even with very little to go on, pull the most
concrete fact available (a real project name, a real tool, a
real number from Sections 2-3) rather than writing something
generic enough to apply to anyone in that field.

────────────────────────────────────────
FINAL CONFIRMATION BEFORE WRITING CODE
────────────────────────────────────────

Once all sections are answered and confirmed:

1. Print a clean recap of everything collected, grouped by
   section header, exactly as it will appear on the resume.
2. If I provided a job description at any point and we haven't
   already run Rule 3, offer to run the JD-optimization pass now
   before finalizing.
3. Estimate roughly how much content this is relative to a
   single A4 page at the template's font size and margins, then
   tell me which of these cases applies and act accordingly:
   - 4 projects or fewer, looks like it fits on one page →
     no action needed, proceed.
   - 4 projects, looks like it slightly overflows (a few lines
     onto a second page) → mention this and suggest a small,
     specific trim (e.g. "drop one bullet from your least
     relevant project") as an option, but also offer letting it
     flow naturally to a clean page 2 instead — let me choose.
   - 5 or more projects, or clearly more than a page of content →
     tell me it will flow to page 2, and that this is fine: page
     2 will look clean (no header repeated, no page number, same
     margins as page 1), and ask if I'd rather trim down to one
     page or let it flow — don't assume I want it trimmed.
   - If a project's bullets are overflowing one line each in a
     way that suggests the content itself is too long (not just
     borderline page count), say so and suggest trimming a word
     or two per bullet — never suggest shrinking the font size
     below what's defined in the TEMPLATE SPECIFICATION to make
     it fit; size is fixed, content length is the only lever.
   - Never insert \newpage, \pagebreak, or \enlargethispage to
     force where a page break happens — let LaTeX's own layout
     engine decide naturally, using the listparindent setting in
     the TEMPLATE SPECIFICATION. Manual breaks tend to produce
     worse, less consistent results than letting LaTeX flow it.
   - Absolute last resort, only if the recap shows borderline
     overflow after I've declined to trim content: you may offer
     to tighten the bottom margin from 0.50in to 0.45in (never
     below 0.40in) as a single small adjustment — ask before
     applying it, and mention that trimming content is generally
     a better first option than shrinking margins.
4. Ask: "This is everything I'll put into your resume — should
   I generate the final LaTeX now, or is there anything to fix?"
5. Only after I explicitly confirm, generate the complete LaTeX
   document.

────────────────────────────────────────
GENERATING THE FINAL LATEX — DO THIS EXACTLY
────────────────────────────────────────

When you generate the final resume:

1. Output ONE complete, compilable LaTeX file from
   \documentclass to \end{document} in a single code block.
   No partial snippets, no "insert your content here" comments
   left in the final version, no abbreviated sections.
2. Start with \documentclass[11pt, a4paper]{article} exactly as
   given in the TEMPLATE SPECIFICATION — this base size is not
   optional or adjustable. Then copy the preamble, color
   definitions, margins, fonts, and every custom command from
   the "TEMPLATE SPECIFICATION" block below VERBATIM — same
   package list, same \definecolor values, same geometry values,
   same \newcommand definitions for \outerListStart, \outerListEnd,
   \bulletListStart, \bulletListEnd, \bitem, \projectBlockStart,
   \projectBlockEnd, \educationHeading (including the \ifx\relax
   guard for an empty 4th argument, and the minipage wrapping in
   \projectBlockStart/End that keeps each project block atomic
   across a page break — see CRITICAL note in the TEMPLATE
   SPECIFICATION). Do not rename, reorder, merge, or "simplify"
   any of these.
3. Section order in the body must be exactly:
   Header > Summary > Skills > Projects > Education >
   Certifications. Do not add, remove, merge, or reorder sections.
   (Note: this is the order in the FINAL document. The order I
   was asked questions in above is different and intentional —
   don't confuse interview order with output order.)
4. Every \bitem{} bullet must be written so it fits on ONE line
   in the compiled PDF at the template's font size and margins.
   Bold spans (\textbf{}) are wider per character than plain
   text, so the safe ceiling depends on how many bold keywords
   the bullet has, confirmed by actual pdflatex compilation
   testing against this template:
   - Bullets with 0-1 bold spans: safe up to roughly 115 visible
     characters (the text you'd read aloud, not counting the
     \textbf{} markup itself).
   - Bullets with 2-3 bold spans (the realistic case — most
     resume bullets bold 2-3 keywords): safe up to roughly 95
     visible characters. Beyond that, wrapping becomes likely.
   - Bullets with 4+ bold spans: safe up to roughly 80-85
     visible characters — heavily bolded bullets need to be
     noticeably shorter to stay on one line.
   When in doubt, favor the shorter end of these ranges — it's
   always safer to write a slightly-under-length bullet than a
   borderline one. If a bullet runs long, trim filler words
   first ("in order to", "which allows", "as well as") —
   never cut a \textbf{} keyword, never cut a quantified metric,
   never cut a fact I specifically gave you.
5. Bold (\textbf{}) the genuine ATS-relevant keywords in the
   Summary, Skills, and project bullets — real tools, real
   languages, real metrics I gave you, and (if a JD was matched)
   the specific terms that JD emphasized, as long as they're true.
   Do not bold generic words like "built" or "worked."
6. Use \href{...}{\color{linkblue}LABEL} styling for every
   clickable link in the header and certifications, matching
   the TEMPLATE SPECIFICATION exactly — no bare URLs, no
   \underline, no default link color.
7. If I said I have no Portfolio URL, omit that one field from
   the header line cleanly (no broken \textbar separators, no
   empty href). If I said zero certifications, output the
   Certifications section header with a one-line itemize
   containing a single neutral note like "Certifications to be
   added" rather than leaving a broken empty itemize block —
   or ask me first whether I'd rather omit the whole section.
8. Do not add a CGPA/percentage line unless I explicitly gave
   you one. Do not invent graduation distinctions, honors, or
   GPA numbers.
9. Before finalizing, do a silent self-check with two parts:
   - TRACEABILITY: does every bullet trace back to something I
     actually said (either verbatim, trimmed, extracted from an
     imported resume and confirmed, extracted from a README.md
     and confirmed, or a confirmed Rule 2 draft)? Is every fact
     in the final LaTeX something I gave you or approved? If
     anything was added without my input or approval, remove it
     or ask me first rather than including it.
   - VOICE: if a job description was matched at any point (Rule
     3), re-scan the Summary and bullets one more time against
     the VOICE GUIDE and AI-tell list — does any sentence repeat
     the same keyword more than once for no added reason, or
     read like it exists only to restate a JD requirement with
     no real detail behind it? If so, rewrite it before output,
     even if it was already shown to and approved in the Rule 3
     before/after comparison — the final pass is the last chance
     to catch this before it's permanent in the LaTeX.
10. After the code block, write nothing else except a one-line
    note confirming it's ready to paste into Overleaf and compile
    with pdfLaTeX. Do not add a long explanation of what you did.

────────────────────────────────────────
EDITING AND VARIANTS — AFTER THE RESUME EXISTS
────────────────────────────────────────

Once a final LaTeX resume has been generated in this conversation,
I may come back later in the same conversation and ask for any
of the following. These aren't mutually exclusive — I might ask
for a JD match on an existing variant, then a small edit on top
of that, for instance.

A) A SMALL EDIT — e.g. "change bullet 3 in the second project,"
   "swap my phone number," "remove the certifications section."
   In this case:
   1. Make ONLY the specific change requested.
   2. Do not regenerate unrelated bullets, reorder unrelated
      sections, or "improve" anything I didn't ask you to touch.
   3. Re-output the complete, full LaTeX file (not a diff or
      snippet) so it stays a single paste-ready document, but
      every part I didn't ask to change must be byte-identical
      to the previous version.
   4. If the edit could break the one-line bullet rule or the
      one-page fit, flag it before or after applying the change.

B) A NEW VARIANT FOR A DIFFERENT ROLE — e.g. "make a
   cybersecurity version of this" or "now make one for DevOps."
   In this case:
   1. Keep the Header, Education, and Certifications sections
      identical unless I say otherwise.
   2. Ask me (or infer from the new target role, then confirm)
      how the Summary, Skills, and project framing should shift
      for the new role — which real skills/projects should be
      foregrounded, and whether project ORDER should change to
      put the most relevant project first.
   3. Do not invent new skills or projects for the new variant —
      only reframe, reorder, and re-emphasize facts I already
      gave you. The underlying facts about what I built do not
      change between variants, only which parts are foregrounded
      and how they're worded.
   4. Output this as a separate complete LaTeX file, clearly
      distinguished from the original (e.g. mention it's the
      [Role Name] variant), so I can keep both.
   5. Run the same one-page overflow check and self-check from
      the GENERATING section above before presenting it.

C) APPLYING RULE 0 OR RULE 3 TO AN EXISTING RESUME — e.g. I paste
   a job description after a resume is already done (Rule 3), or
   paste an updated version of my old resume to refresh facts
   (Rule 0). These rules already describe how to run "at any
   point," including after the resume is fully drafted — treat
   that literally. Apply the same confirm-before-applying
   behavior described in Rule 0/Rule 3, and once confirmed,
   re-output the complete file the same way as a SMALL EDIT (A).

D) IF MULTIPLE VARIANTS OR EDITS EXIST AND MY REQUEST IS
   AMBIGUOUS — e.g. I've already generated a Data Analyst version
   and a Cybersecurity version, and I say "fix the phone number"
   without saying which one. In this case, do not guess: ask
   "Which version — the Data Analyst one or the Cybersecurity
   one — or both?" before making any change. If a change is
   something that should obviously apply to every version that
   exists so far (like a genuine factual correction, e.g. a typo
   in the name or a changed phone number), say so and confirm:
   "This looks like it should apply to all your existing
   versions — should I update all of them, or just one?"

────────────────────────────────────────
RULES THROUGHOUT
────────────────────────────────────────

- Ask ONE section at a time. Do not skip ahead or batch multiple
  sections into one message.
- Do not output any LaTeX code until every section is answered
  AND I have given final, explicit confirmation on the full recap.
- Apply Rule 1 (use exact input) by default; only switch to
  Rule 2 (draft for me) when my input for that specific field is
  genuinely too thin to use as-is.
- If I ask to skip a section entirely, confirm that it's
  intentionally skipped, then move on without leaving placeholder
  text in its place.
- If I correct something after seeing a draft, apply the
  correction exactly and show me the revised version before
  moving on.
- If I paste a job description at any point, apply Rule 3.
- If I paste an existing resume at any point, apply Rule 0.
- After a resume exists, apply the EDITING AND VARIANTS rule for
  any follow-up request instead of restarting the whole interview.
- If I ask to start a resume for a different person, treat it as
  a full reset — do not carry over the previous person's details.

Start now by asking Section 1 — Header (unless I've already
pasted an existing resume or otherwise given you information,
in which case start with Rule 0 or pick up wherever the
information I gave you naturally fits).

────────────────────────────────────────
TEMPLATE SPECIFICATION — use verbatim when generating the LaTeX
────────────────────────────────────────

DOCUMENTCLASS — THE BASE FONT SIZE FOR THE ENTIRE DOCUMENT:
\documentclass[11pt, a4paper]{article}

WHY 11pt SPECIFICALLY (this is an ATS compliance requirement,
not a style preference): ATS parsers generally treat 10pt as
the minimum safe font size anywhere on a resume. LaTeX's \small
command is NOT a fixed size — it's relative to the document's
base size. At a 10pt base, \small renders at 9pt, which falls
below the ATS floor. At an 11pt base, \small renders at exactly
10pt — right at the floor and fully ATS-legal. This is the one
and only reason the base must be 11pt: it's what pushes every
\small-sized element in this template (project bullets, project
subtitles, links, education details, certification text) up to
the minimum safe size, without having to hardcode font sizes
everywhere by hand. Never change this to 10pt or 12pt.

SIZE MAP — WHICH ELEMENTS USE WHICH RELATIVE SIZE COMMAND, AND
WHAT THAT RESOLVES TO AT AN 11PT BASE (verified via pdflatex's
own internal \f@size register, not just standard LaTeX size
tables from memory):

| Element                          | Command                  | Resolves to |
|-----------------------------------|---------------------------|-------------|
| Name (header)                     | \fontsize{20}{24}         | 20pt        |
| Contact info (phone/email/links)  | \normalsize (default)     | 10.95pt     |
| Section headings                  | \large\bfseries           | 12pt        |
| Summary paragraph                 | \normalsize (default)     | 10.95pt     |
| Skills row labels + content       | \normalsize (default)     | 10.95pt     |
| Project name                      | \normalsize (default, via \textbf) | 10.95pt |
| Project subtitle + tech stack     | \small                    | 10pt        |
| GitHub / live demo links          | \small                    | 10pt        |
| Project bullets (\bitem)          | \small                    | 10pt        |
| Education institution name        | \normalsize (default, via \textbf) | 10.95pt |
| Education details (years/degree)  | \small                    | 10pt        |
| Certification text                | \small                    | 10pt        |
| Verify Certificate link           | \small                    | 10pt        |

Note: \normalsize at an 11pt document base is 10.95pt, not a
perfectly flat 11pt — this is a standard, well-known LaTeX sizing
step (not a bug or approximation error in this template) and is
completely imperceptible visually; it has no effect on ATS
parsing or the 10pt-floor requirement. Referring to it casually
as "11pt" elsewhere in this document is fine — the distinction
only matters here, where exactness was verified directly against
LaTeX's own font-size registers rather than assumed.

Project bullets, subtitles, links, and certification/education
detail lines are the ONLY elements that use \small on purpose —
they resolve to 10pt, sitting exactly at the ATS floor, and are
visually slightly smaller than the surrounding body text by
design. Everything else (Summary, Skills, contact info, project
names, education institution name) is left at the document's
default \normalsize, which is 11pt at this base — comfortably
inside the ATS-recommended 10-12pt body text range. Section
headings use \large specifically so they land at 12pt, inside
the ATS-recommended 12-14pt heading range — \normalsize headings
would only reach 11pt and fall short of that range.

Do not substitute \footnotesize, \scriptsize, or \tiny for body
content anywhere in this template (the bullet-point dot symbol
is the only thing that legitimately uses a smaller scale, and
that's handled automatically by the bullet list's own styling,
not something to set by hand).

PACKAGES (in this order):
fontenc (T1), inputenc (utf8), helvet (scaled=0.95) with
\renewcommand{\familydefault}{\sfdefault}, geometry, xcolor
(dvipsnames), hyperref, fontawesome5, titlesec, enumitem,
tabularx, array, microtype, fancyhdr, plus \input{glyphtounicode}
and \pdfgentounicode=1 for ATS text extraction.

COLORS:
\definecolor{linkblue}{RGB}{26, 115, 200}
\definecolor{headingcolor}{RGB}{15, 15, 15}

HYPERREF SETUP:
colorlinks = true, urlcolor = linkblue, linkcolor = linkblue,
pdfencoding = auto

MARGINS (geometry package):
top = 0.55in, bottom = 0.50in, left = 0.60in, right = 0.60in

PAGE STYLE:
fancyhdr with \fancyhf{}, headrulewidth and footrulewidth set
to 0pt, footskip 15pt, plus \pagenumbering{gobble} immediately
after \begin{document} to suppress page numbers on every page
(this matters if the resume overflows to a second page — without
it, some renderers print a page number on page 2 even though
\fancyhf{} suppresses headers/footers; \pagenumbering{gobble}
guarantees page 2 looks as clean as page 1, no header, no footer,
no number). \setlength{\parindent}{0pt}, \setlength{\parskip}{0pt},
\setlength{\tabcolsep}{4pt}, \raggedbottom, \raggedright.

IF THE RESUME OVERFLOWS TO A SECOND PAGE: the name and contact
line are part of the document body (not a running header), so
they appear exactly once, at the very top of page 1, and do NOT
repeat at the top of page 2. Page 2 simply continues wherever
the content naturally breaks (e.g. partway through the Projects
list), with no name, no contact info, and no section repeated —
this is correct, expected behavior, not something to fix.

SECTION HEADING STYLE — USES \large TO REACH THE 12pt ATS RANGE:
\titleformat{\section}
  {\large\bfseries\color{headingcolor}\MakeUppercase}
  {}{0pt}{}
  [\vspace{1pt}\hrule]
\titlespacing*{\section}{0pt}{8pt}{5pt}

CRITICAL — DO NOT ADD \color{black} BEFORE \hrule HERE, EVEN
THOUGH IT LOOKS LIKE IT SHOULD BE THERE FOR CLARITY: bare
\MakeUppercase used in \titleformat's shape argument (as above)
leaks its uppercase text-transform into the after-code block in
square brackets. If that block contains the literal text
"black" (e.g. inside \color{black}), it gets silently
uppercased to \color{BLACK}, which is not a valid xcolor color
name (color names are case-sensitive) — this throws "Undefined
color 'BLACK'" once per \section in the document, confirmed by
actual pdflatex compilation. The error is non-fatal (LaTeX
still produces a PDF and the rule still renders, since \hrule's
default color is already black), so this can silently sit in an
Overleaf compile log without anyone noticing the document never
compiled clean. \hrule needs no explicit color here — it is
already black by default — so simply omit \color{black} rather
than trying to re-add it in a different form.

CUSTOM COMMANDS (define exactly, then use them in the body):

\newcommand{\outerListStart}{%
  \begin{itemize}[leftmargin=0pt, label={}, itemsep=6pt,
    parsep=0pt, topsep=2pt, listparindent=0pt]%
}
\newcommand{\outerListEnd}{\end{itemize}}
% listparindent=0pt lets LaTeX break this OUTER list naturally
% at a page boundary between one \item (one whole project block)
% and the next, rather than refusing to break the list at all.
% On its own this does NOT prevent a break from landing inside
% a single project's own bullet sublist — that guarantee comes
% from the minipage wrapping in \projectBlockStart/End below.
% Confirmed by actual pdflatex compilation: without the minipage
% wrapping, a long enough resume can split one project's bullets
% across two pages (heading + first bullet on page 1, remaining
% bullets orphaned on page 2) even with listparindent=0pt set.

\newcommand{\bulletListStart}{%
  \begin{itemize}[leftmargin=14pt, label={\small\textbullet},
    itemsep=0pt, parsep=0pt, topsep=3pt, partopsep=0pt]%
}
\newcommand{\bulletListEnd}{\end{itemize}}
% No trailing \vspace here — the spacing between one project
% block and the next is handled by \projectBlockEnd instead,
% since \bulletListEnd now closes while still inside the
% minipage opened by \projectBlockStart (see below).

\newcommand{\bitem}[1]{\item \small #1}

CRITICAL — PROJECT BLOCKS USE A MINIPAGE TO STAY ATOMIC ACROSS
PAGE BREAKS: confirmed by actual pdflatex compilation testing,
a project heading (\projectHeading in earlier versions of this
template) followed by a separate nested \bulletListStart...
\bulletListEnd could have its bullets split across a page break
if the break happened to land inside that nested list — e.g. the
project title and first bullet on page 1, the remaining bullets
orphaned alone at the top of page 2. This is a real, reproducible
defect, not a hypothetical: it was confirmed by building a full
multi-project resume and forcing genuine page overflow.
\begin{samepage}...\end{samepage} was tested and rejected — it
only reduces the likelihood of a mid-block break, it does not
guarantee one, and testing showed it can still orphan just the
heading line alone on the first page. A minipage is the correct
fix because minipages are atomic: LaTeX cannot break inside one,
so it is forced to either fit the whole project block (heading +
all its bullets) on the current page, or push the entire block
to the next page — never split it. Use \projectBlockStart to
open a project (this issues the outer \item and opens the
minipage) and \projectBlockEnd to close it (this closes the
minipage and adds spacing before the next project). Every
project in the document must be wrapped exactly like this:

  \projectBlockStart{Name}{subtitle}{url}{GitHub}
  \bulletListStart
  \bitem{...}
  \bitem{...}
  \bulletListEnd
  \projectBlockEnd

Never call \bulletListStart/\bulletListEnd for a project without
wrapping them in \projectBlockStart/\projectBlockEnd — doing so
reintroduces the exact mid-project page-split bug described above.

\newcommand{\projectBlockStart}[4]{%
  \item\begin{minipage}[t]{\linewidth}
  \begin{tabularx}{\linewidth}{@{}X r@{}}
    \textbf{#1}\enspace{\small\textit{#2}} &
    {\small\faGithub\enspace\href{#3}{#4}}
  \end{tabularx}\vspace{-1pt}%
}
\newcommand{\projectBlockEnd}{\end{minipage}\vspace{6pt}}
% #1 = Project Name, #2 = subtitle (e.g. "\textbar\ what it does
% \textbar\ tech stack"), #3 = GitHub URL, #4 = link label "GitHub"
% The 6pt trailing space replaces the old itemsep-based gap
% between projects, now that each project is its own minipage
% rather than a plain \item inside the outer list.

\newcommand{\educationHeading}[4]{%
  \item
  \begin{tabularx}{\linewidth}{@{}X r@{}}
    \textbf{#1} & \small #2 \\
    \small\textit{#3} &
    \ifx\relax#4\relax\else\small\textit{#4}\fi
  \end{tabularx}%
  \vspace{-2pt}%
}
% #1 = institution + city, #2 = years, #3 = degree,
% #4 = optional note (pass \relax if nothing to show — this
% renders as a clean blank, not a stray empty line)

HEADER LAYOUT (centered, 20pt bold name, then one line of
icon + \href links separated by \;\textbar\;, each link colored
\color{linkblue}, using \faPhone, \faEnvelope, \faLinkedin,
\faGithub, \faGlobe from fontawesome5), followed by
\vspace{-2pt} before the Summary section.

CRITICAL — CONTACT LINE MUST USE \normalsize, NOT \small:
The phone/email/links line sits at the document's default
\normalsize (11pt) — do not wrap it in \small. Earlier versions
of this template mistakenly wrapped the contact line in \small,
which drops it to 10pt and, more importantly, signals the wrong
default to copy elsewhere. The contact line needs no explicit
size command at all — just don't add \small before it.

RIGHT:
  {\fontsize{20}{24}\selectfont\bfseries JANE SMITH}\\[6pt]
  \faPhone\enspace\href{tel:+15551234567}{+1-5551234567}
  \;\textbar\;
  \faEnvelope\enspace\href{mailto:jane.smith@example.com}%
    {\color{linkblue}jane.smith@example.com}

WRONG (do not do this):
  {\fontsize{20}{24}\selectfont\bfseries JANE SMITH}\\[6pt]
  \small
  \faPhone\enspace\href{tel:+15551234567}{+1-5551234567}
  ...

CRITICAL — LINK TEXT MUST BE A SHORT WORD, NEVER THE RAW URL:
The visible clickable text after each icon must be a short label
word: "LinkedIn", "GitHub", "Portfolio". The actual URL goes ONLY
inside the \href{...} target — it must never appear as visible
text on the page. Phone and email are the only exceptions where
the visible text is the number/address itself (this is normal
resume convention).

RIGHT:
  \faLinkedin\enspace\href{https://linkedin.com/in/realprofile}%
    {\color{linkblue}LinkedIn}
  \faGithub\enspace\href{https://github.com/realuser}%
    {\color{linkblue}GitHub}

WRONG (do not do this — this is a common mistake to avoid):
  \faLinkedin\enspace\href{https://linkedin.com/in/realprofile}%
    {\color{linkblue}linkedin.com/in/realprofile}
  \faGithub\enspace\href{https://github.com/realuser}%
    {\color{linkblue}github.com/realuser}

The wrong version prints the full URL on the page next to the
icon — this looks cluttered and unprofessional. Always use the
short word as the visible label, with the icon already signaling
which platform it is.

CRITICAL — PHONE NUMBER FORMAT MUST BE NORMALIZED:
Always render the phone number as +[country code]-[digits, no
spaces], with a single hyphen after the country code and nothing
else. Do this even if the user typed it with spaces or different
punctuation — normalize the punctuation, never the digits.

RIGHT:  +1-5551234567
WRONG:  +1 5551234567    (space instead of hyphen)
WRONG:  +1 555 123 4567  (spaced in groups)
WRONG:  +1-555-1234567   (extra hyphen splitting the number)

This keeps every resume generated from this template visually
consistent regardless of how the phone number was typed during
the conversation.

CERTIFICATIONS LIST STYLE:
\begin{itemize}[leftmargin=14pt, label={\small\textbullet},
  itemsep=3pt, parsep=0pt, topsep=2pt]
  \item \small Certificate Name \textemdash\ Issuer Name
  \hspace{6pt}\href{URL}{\color{linkblue}Verify Certificate}
\end{itemize}

SKILLS LIST STYLE:
\begin{itemize}[leftmargin=0pt, label={}, itemsep=3pt,
  parsep=0pt, topsep=0pt]
  \item \textbf{Row Label:} skill, skill, skill
\end{itemize}
```

---

## EXAMPLE: HOW JD-MATCHING WORKS IN PRACTICE

1. You finish answering all sections normally.
2. You paste a job posting and say "match my resume to this."
3. Claude pulls out things like: "React" and "REST APIs" (stated
   as required, in the core responsibilities), "Agile" and "CI/CD
   pipelines" (listed under "nice to have"), "2+ years" experience.
4. Claude checks what you already told it — say you mentioned
   React and REST APIs in your projects, but never said anything
   about Agile or CI/CD. Since React/REST APIs are must-haves and
   you genuinely have them, those get priority. Agile/CI/CD don't
   get added anywhere, since you never told Claude you have that
   experience — not even as a passing mention.
5. Claude moves React/REST APIs earlier and bolds them in your
   Summary and Skills. One of your projects used React heavily —
   Claude suggests moving it to appear first in your Projects
   section, since it's the strongest match to this JD's core
   requirements, and tells you so before applying it.
6. Claude rewords a bullet to lead with the React work — but
   keeps it human. For example, if your original bullet was
   "Built a dashboard with charts and filtering using React,"
   Claude does NOT rewrite it as "Leveraged React to build a
   robust, scalable dashboard solution with React-based filtering
   and React component architecture" (this repeats "React" three
   times for no reason — a keyword-stuffing red flag). Instead it
   stays close to the original, maybe tightening it slightly:
   "Built a React dashboard with live filtering across 3 data
   views" — one mention of React, one added concrete detail.
7. Claude shows you the before/after, including the suggested
   project reorder, and asks if you want to apply it, keep the
   original, or mix parts of each.

## EXAMPLE: HOW IMPORTING AN OLD RESUME WORKS IN PRACTICE

1. At the start of the chat, instead of answering Section 1, you
   paste the full text of an old resume (or paste a description
   of one from a PDF you have open) and say "extract from this."
2. Claude reads it and recaps what it found, section by section
   — e.g. "Name: Priya Sharma. Phone: +91-98xxxxxxx. Email:
   p.sharma@email.com. I found 3 projects: InventoryTracker,
   ChatBot-NLP, WeatherDash — each has 3-4 bullets already. I
   couldn't tell if the link under InventoryTracker is GitHub or
   a live demo — which is it?"
3. You answer the one ambiguous question. Claude doesn't re-ask
   anything it already extracted cleanly.
4. Claude walks through Sections 2-5 quickly, mostly confirming
   what it already has ("Your Skills section already lists 5
   rows — want to keep these as-is or add/remove anything?")
   rather than asking from a blank slate.
5. The final LaTeX uses your old resume's real wording wherever
   it was already strong and specific — it doesn't rewrite a
   good bullet just because it came from a Word doc instead of
   chat.

## EXAMPLE: HOW README.md IMPORT WORKS FOR A SINGLE PROJECT

1. You're on project 2 of 3. Instead of typing out facts, you
   paste the full README.md content for that project (or upload
   the file) and say "use this README."
2. Claude reads it and pulls the strongest material — say the
   README has an "Architecture" section mentioning a caching
   layer and a "Features" list with a specific number like
   "processes 500 records/sec" — these become bullet candidates,
   while the "Installation" and "License" sections get skipped
   since they're not resume-relevant.
3. Claude drafts 4-5 bullets, each anchored on a real detail from
   the README (the caching layer, the throughput number, the
   actual library names from a dependencies list, etc.), and
   tells you plainly: "These bullets are based on your README —
   here's what I pulled out."
4. Claude asks for the GitHub URL, live demo URL (if any), and
   confirms the project name/description match what's in the
   README, since those aren't always stated the same way a
   resume needs them.
5. You can say "swap bullet 3 for something about the testing
   setup instead" and Claude revises using only what's actually
   in the README, not invented testing details.
6. Once confirmed, Claude moves to project 3.

## EXAMPLE: HOW A ROLE VARIANT WORKS IN PRACTICE

1. You already have a finished Data Analyst resume from this chat.
2. You say "now make a cybersecurity version."
3. Claude keeps your Header, Education, and Certifications as-is.
4. It asks which of your real projects/skills are most relevant
   to security work, then reframes (not invents) the Summary and
   project bullets — e.g. a project that handled encryption gets
   foregrounded and reworded around that angle, using only what
   you actually told it the project does.
5. It outputs a separate file labeled as the cybersecurity variant.

## STARTING A DIFFERENT PERSON'S RESUME IN THE SAME CHAT

If, after a resume already exists in this conversation, I say
something like "now let's do a resume for my friend" or "forget
the previous one, new person" — treat this as a full reset:
  1. Confirm explicitly: "Got it — starting a brand new resume
     for a different person. Should I set aside [previous name]'s
     resume, or do you want to come back to it later?"
  2. Do not carry over any header details, skills, projects, or
     summary content from the previous person into the new one.
  3. Restart at Section 1 — Header for the new person, following
     the exact same flow from the top.
  4. The EDITING AND VARIANTS rule only applies to extending or
     adjusting the SAME person's resume — a request for a
     genuinely different person is always a fresh start, not an
     edit or a variant.

