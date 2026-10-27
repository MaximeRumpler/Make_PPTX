# Private mode

For decks whose content you cannot share with an AI assistant: unreleased results, salaries, client names, anything under a confidentiality agreement. This is an advanced page. For most decks you do not need it: the [quick choices](get-started.md#5-the-quick-choices-it-asks-about) are enough.

**Never paste secrets into a brief or a chat**: passwords, access keys, personal data of other people, or anything you are not allowed to share. The assistant sends what you type to its provider. Private mode is about not having to type it at all.

* * *

## Three levels

| **Level** | **How it works** | **Status** |
|:---|:---|:---|
| **1. Structure only** | You describe the deck without its content ("slide 2: one key figure; slide 3: three reasons"). The skill builds a *skeleton deck*: each box holds an instruction with its length limit, such as `[Title, max 52 characters]`, and charts hold dummy data named "Dummy data — replace". You open it in PowerPoint or LibreOffice and type your content on your own computer. | Available |
| **2. Fill offline and rebuild** | Same start, but you type your content into the fill sheet that comes with the skeleton, and a script on your computer builds the finished deck from it. | Planned |
| **3. Pseudonymise and restore** | Names and figures in your notes are replaced by neutral tokens (*Client A*, *Figure 1*) before the assistant sees them, and put back on your computer after the deck is built. | Planned |

### What the assistant sees

| **Level** | **The assistant sees** | **The assistant never sees** |
|:---|:---|:---|
| 1. Structure only | The number of slides, what kind of slide each one is, and any wording you choose to give | Your text, figures, names and chart data |
| 2. Fill offline and rebuild | The same as level 1 | The same as level 1, also once the deck is finished |
| 3. Pseudonymise and restore | Your notes with tokens in place of names and figures | The real names and figures, and the table that links them to the tokens |

* * *

## Make a skeleton deck (level 1)

Ask in your own words, and give only the structure:

```text
Make a board deck. I can't share the real content: make a skeleton I can fill in.
1. Cover
2. One key figure with a short explanation
3. Three reasons behind it
4. A chart comparing two periods across five categories
5. The decision we ask for
```

You get two files:

- **the deck**, with an instruction in every box and the list of boxes and limits in the speaker notes of each slide;
- **a fill sheet** (`<deck>.fill-sheet.md`): slide, box and length limit, to keep at hand while you type.

Type your content in PowerPoint or LibreOffice, replace the dummy chart data (*right-click the chart → Edit Data*), then delete the speaker notes if you do not want them in the shared file. To see what is left to fill, ask the assistant to run `lint_deck.py` on the deck on your computer (Claude Code, Codex and other local assistants), or just look for square brackets.

The deck is marked *Confidential* in the footer, uses only the icons the skill carries, and keeps no author or keywords in its file properties.

* * *

## Offline use

The skill's own tools can work without any internet connection: with `--offline`, nothing they do reaches the network. They use the slide libraries and the 1,900 icons bundled with the skill, and your own files. Anything that would need the internet, such as a photo search or an online icon set, is skipped with a plain message instead.

Offline here means the skill. Your AI assistant itself still needs its usual connection, and whatever you type in the chat goes to it. In Claude.ai and Claude desktop the tools run on Claude's side; in Claude Code, Codex, Cursor, Copilot and Gemini CLI they run on your computer.

[Back to Get started](get-started.md)
