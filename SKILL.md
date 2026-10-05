---
name: cite-creator
description: Create a debate evidence citation (cite) from information the user gives (URL, article, author, quals, date) in either the Cal / UC Berkeley format or the CME / Lynbrook format. Use when the user asks to cite, make a cite, format a citation, or write quals for a debate card.
---

# Cite Creator

Produce one debate citation, formatted exactly to the requested guide. Output the citation and nothing else.

**Em dash override:** any global "no em dashes" preference (e.g. in AGENTS.md) does NOT apply to this skill or project. Use em dashes (`—`, U+2014) wherever the formats, references, or examples use them; never convert them to hyphens.

## 1. Pick the format

| User says | Read |
| --- | --- |
| "Cal", "UC Berkeley", "Berkeley" | `references/cal.md` |
| "CME", "Lynbrook" | `references/lynbrook.md` |

Read the matching reference file before writing anything. Follow its templates, punctuation, and examples exactly; do not mix conventions between the two formats. If the user names no format, ask which one before writing.

## 2. Gather source details

Collect: every author's full name, publication date, publication/outlet, title, and URL (plus volume/issue/pages for journals, chapter/pages for books, court and reporter citation for court cases).

- Use what the user provided. If they gave a URL or article, read it for anything missing.
- Never invent a date, title, author, or URL. If a field cannot be determined after checking the source, follow the guide's fallback (e.g. year only, volume/pages instead of URL).
- Sanitize URLs: drop tracking parameters (`utm_*`, `fbclid`, `gclid`, etc.), AMP variants, and fragments. Prefer a DOI for journal articles.
- Use the most specific date the source gives (full date when available, else month and year, else year).

## 3. Qualifications

**If the user provided qualifications, use their wording exactly as given. Do not research, rewrite, shorten, or add to them.** Format punctuation (separators, trailing periods) still applies.

Otherwise research each author (author bio on the article, institutional page, LinkedIn, faculty profile) and write qualifications that are:

- **Relevant:** only credentials that support the author's credibility on this article's topic. Drop unrelated roles, awards, hobbies, and filler.
- **Short:** usually one to three comma-separated items per author. Current position first, then the most relevant former role or degree.
- **Scannable:** debaters read these mid-round under time pressure. Lead with the title and institution; cut verbiage like "currently serves as", "is a", "has been", "where they focus on".

| Too long | Good |
| --- | --- |
| Dr. Jane Smith currently serves as a Senior Fellow at the Brookings Institution, where she focuses on nuclear policy, and previously spent ten years working in various roles at the State Department after receiving her PhD in Political Science from Stanford. | Senior Fellow at Brookings, former State Department nonproliferation official, PhD in Political Science from Stanford. |

## 4. Time-sensitive or standard

Check today's date. Use the time-sensitive variant only if the evidence was published within one month of today's date. This one-month threshold overrides the guides' "two months" wording. Everything else uses the standard template.

## 5. Output

Output only the formatted citation:

- No `TAG.` line, no "Tag" prefix, no label, no code fence, no commentary before or after.
- Bold the oral cite with Markdown `**...**` exactly where the reference file shows it.
- Use curly quotes and the exact separators the format requires. The em dash in the Cal separator (`—`) is required by that format.
- Multi-line Lynbrook citations (three or more authors) keep one line per author as in the reference file.
