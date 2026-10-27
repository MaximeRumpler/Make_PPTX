# Get started

Make a clean PowerPoint deck from your own notes, with the AI assistant you already use. No coding needed.

This page covers **Make_Clean_PPTX**, the skill of the set that is available today. Make_Style_PPTX (another look) and Make_Colors_PPTX (your brand) are in preparation and will install the same way.

**On this page:** [Install](#1-install) · [Check](#2-check-that-it-works) · [What to give it](#3-what-to-give-it) · [Requests to copy](#4-requests-to-copy) · [The quick choices](#5-the-quick-choices-it-asks-about) · [Questions](#6-questions-and-problems)

* * *

## 1. Install

Pick the assistant you use. Each takes about two minutes.

### Claude.ai or Claude desktop

1. Download [**make-clean-pptx.zip**](https://github.com/MaximeRumpler/Make_Clean_PPTX/releases/latest/download/make-clean-pptx.zip). Keep it as a zip; do not unzip it.
2. In Claude, open *Settings → Capabilities* and turn on **Code execution and file creation**. The skill writes the deck with a small program, so it cannot work without this.
3. Still in *Capabilities*, under *Skills*, click **Upload skill** and choose the zip.

Python is already there on Claude's side: you have nothing else to install.

### Claude Code

Type these two lines in Claude Code, one after the other:

```text
/plugin marketplace add MaximeRumpler/Make_Clean_PPTX
/plugin install make-clean-pptx@make-clean-pptx
```

Then restart Claude Code.

### Codex, Cursor, GitHub Copilot, Gemini CLI and others

1. Install [Node.js](https://nodejs.org) if you do not have it (it provides the `npx` command).
2. Open a terminal and run:
   ```text
   npx skills add MaximeRumpler/Make_Clean_PPTX
   ```
3. It asks which assistant you use: choose yours, then restart the assistant.

These assistants run the skill on your own computer, so it needs [Python](https://www.python.org/downloads/) 3.9 or newer. Most computers have it; the next step tells you if yours does not.

**Updating later:** in Claude Code, `/plugin marketplace update MaximeRumpler/Make_Clean_PPTX`; in Claude.ai, upload the new zip; elsewhere, run the `npx skills add` line again.

* * *

## 2. Check that it works

Ask your assistant:

```text
Run the doctor script of the make-clean-pptx skill with --fix and tell me what it says.
```

The skill checks that it has everything it needs, installs missing Python packages when it can, and answers in one plain sentence. "Everything the skill needs is installed" means you are ready. If it names something to install, see [Questions and problems](#6-questions-and-problems).

You can skip this step: the skill runs the same check by itself when something is missing.

* * *

## 3. What to give it

Paste the text into the chat or attach the file. The more of your own content it gets, the better the deck.

| **Works well** | **Example** |
|:---|:---|
| Raw notes | Bullet points from a meeting, even messy ones |
| A report or long document | A Word file, a PDF, a web page you copied |
| A table of figures | Sales by quarter, a budget against actuals, survey results |
| An outline | One line per slide, or just the parts you want |
| An existing deck | A `.pptx` to review, clean up or rebuild |
| A filled-in brief | The [brief template](brief-template.md), for the best result on the first try |

**What it will not do**

- **Invent figures, quotes or names.** If a slide needs a number you did not give, it picks a text slide instead, or asks you. Check any figure it flags in its final message.
- **Write the deck from a topic alone.** With only "a deck about our new product", it asks for the key points rather than making them up.
- **Overwrite your file.** When it reviews a deck, it saves the new one next to it, as `<name>-clean.pptx`.
- **Apply your brand.** The slides are black, grey and white. Apply your company's PowerPoint theme (*Design → Themes*) and they switch to your colours and fonts.

* * *

## 4. Requests to copy

Copy a request, then paste or attach your content after it. Write in your own words if you prefer: the skill understands plain English and French.

**Common decks**

```text
Make a 10-slide board deck from this quarterly report. Lead with the decision we need.
```
```text
Make a 12-slide pitch deck from these notes: problem, solution, market, traction, team, ask.
```
```text
Make a workshop deck from this agenda: one slide per exercise, with the timing on each.
```
```text
Make a project review deck from this status report: progress, risks, next steps.
```
```text
Turn this table of figures into 6 slides with charts. One message per slide.
```
```text
Review my-deck.pptx and make it look professional. Keep my content.
```

**Variations to add to any request**

| **You want** | **Add** |
|:---|:---|
| A short deck | `in 5 slides` |
| A file for LibreOffice | `as a LibreOffice .odp file` |
| Speaker notes | `with speaker notes for each slide` |
| Icons | `with an icon on each key point` |
| A deck in French | `in French` (or write the request in French) |
| A specific audience | `for a non-technical audience`, `for the finance team` |
| A deck to fill in yourself | `I can't share the real content: make a skeleton I can fill in` |

Example deck made from a page of notes: [download it](https://github.com/MaximeRumpler/Make_Clean_PPTX/releases/latest), with the [notes it came from](https://github.com/MaximeRumpler/Make_Clean_PPTX/blob/main/examples/sample-content.md).

* * *

## 5. The quick choices it asks about

Before it starts, the skill may send one short message with a few choices. Reply with the letters (for example `1a 2a 3a 4a`) or in plain words. Every choice has a default, and **the defaults add nothing**: a normal PowerPoint file, no label, no extra steps. If you already said what you want, it does not ask.

| **Choice** | **Options** | **What changes** |
|:---|:---|:---|
| **Format** | PowerPoint `.pptx` (default), LibreOffice `.odp`, or both | The file you get. Keynote and Google Slides open the `.pptx`. |
| **Confidentiality** | No label (default), internal, confidential, or "I can't share the real content" | *Internal* or *Confidential* is written in the slide footers. With *confidential*, the skill uses only the icons it carries and searches nothing online, since a search would reveal the topic. If you cannot share the content, you get an empty skeleton with instructions in each box, to fill in on your own computer. |
| **Length** | About 8 slides (default), shorter, or longer | The number of slides. |
| **Accessibility** | Standard (default) or extra care | Every deck already gets readable contrast, clear titles and a language tag. *Extra care* adds descriptions to images, labels that do not rely on colour alone, and a short note of what to check by hand. |

These options help you prepare a deck. They are not a certification: the skill never calls a deck "compliant". If you need a formal check against an accessibility standard, ask for it separately.

* * *

## 6. Questions and problems

**Where is my file?**
The assistant gives the full path in its last message. In Claude.ai and Claude desktop, the file appears in the chat with a download button. In the other assistants, it is in the folder you were working in, often under `build/`.

**How do I open a `.pptx`?**
Double-click it if you have PowerPoint or LibreOffice. On a Mac, Keynote opens it. Without either, upload it to Google Slides (*File → Import slides*) or open it with the free [LibreOffice](https://www.libreoffice.org).

**It says Python is missing or too old.**
Only for Claude Code, Codex, Cursor, Copilot and Gemini CLI. Install Python 3.9 or newer from [python.org](https://www.python.org/downloads/) (on Windows, tick *Add Python to PATH* during setup), restart your assistant, and ask again.

**It says some Python packages are missing.**
Ask it to run the doctor script with `--fix` (see [step 2](#2-check-that-it-works)). If that fails, it tells you the one command to run.

**It says the visual check was skipped.**
That is fine: the deck is built and checked for text that overflows. The extra check, which looks at each slide as an image, needs LibreOffice on your computer. It is optional. To turn it on, install [LibreOffice](https://www.libreoffice.org) (and on Linux or macOS, poppler, as the message says).

**Nothing happens in Claude.ai: it writes text instead of a file.**
Check that *Code execution and file creation* is turned on (step 1), and that the skill is switched on in *Settings → Capabilities → Skills*. Then start a new chat.

**The assistant does not seem to use the skill.**
Say it explicitly: "Use the make-clean-pptx skill to make a deck from this." In Codex, Cursor or Copilot, restart the assistant after installing.

**Some slides have figures I did not give.**
That should not happen. Tell the assistant which slide, and ask it to remove anything that is not in your content.

**I want other colours, fonts or a different look.**
Apply your company's PowerPoint theme to the deck (*Design → Themes* in PowerPoint): every colour and font follows it. Two more skills, Make_Style_PPTX and Make_Colors_PPTX, are in preparation for looks and brands.

**Still stuck?**
Open an issue on [Make_Clean_PPTX](https://github.com/MaximeRumpler/Make_Clean_PPTX/issues) with your assistant, your system, what you asked and the message you got.
