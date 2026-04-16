# I Built a Markdown Viewer Because AI Gave Me Too Much Markdown

**TL;DR:** Working with Claude Code and other GenAI tools means drowning in Markdown files — memory files, specs, changelogs, prompts. I needed a way to quickly view and compare them, offline, with no install. Nothing fit, so I built [MD/MDX Viewer](https://github.com/samueldratwa-TG/MDreader): a single HTML file (~188KB) you double-click to open. Dual-pane comparison, RTL support, dark mode, zero dependencies.

---

## The problem nobody warned me about

If you work with Claude Code, you know the drill. Everything is Markdown. Your `CLAUDE.md` instructions file. Your memory files. Your project specs. Your changelogs. Your prompt templates. Every conversation you export, every piece of documentation you generate — it's all `.md`.

And it piles up fast.

I found myself constantly alt-tabbing between raw text files, squinting at nested headers and bullet points, trying to mentally render what a document actually looks like. Worse, I often needed to compare two versions side by side — a spec before and after edits, or Hebrew and English translations of the same document.

So I went looking for a simple Markdown viewer. My requirements were modest:

- **Offline.** No uploading files to some cloud service.
- **Zero-install.** No `npm install`, no Electron app, no VS Code extension dependency.
- **Lightweight.** Just let me open a file.
- **RTL support.** I work in Hebrew regularly. Most tools butcher right-to-left text.
- **Side-by-side comparison.** Two panes, synced scrolling.

I couldn't find a single tool that checked all five boxes.

## So I built one

MD/MDX Viewer is a single HTML file. That's it. One file, roughly 188KB, containing everything it needs — [marked.js](https://github.com/markedjs/marked) for Markdown parsing and [highlight.js](https://highlightjs.org/) for syntax highlighting, both embedded inline. No external dependencies, no CDN calls, no build step.

You double-click it. It opens in your browser. You drag in a Markdown file. Done.

Here's the part that still makes me smile: I built the whole thing in one session with Claude Code. An AI-powered coding assistant helped me build a tool for viewing AI-generated content. The snake eats its own tail.

## What it actually does

**Dual-pane layout.** Load a different file in each pane. I use this constantly for comparing document versions — before/after an edit pass, or placing a Hebrew translation next to the English original.

**RTL/LTR toggle per pane.** Click a button and the pane switches direction. This sounds like a small thing until you've tried reading Hebrew in a viewer that forces left-to-right. Each pane is independent, so you can have English on the left and Hebrew on the right, each rendered correctly.

**Scroll sync.** When you scroll one pane, the other follows. Essential for parallel reading during comparison.

**Dark and light themes.** Because it's 2026 and we still can't agree on backgrounds.

**Syntax-highlighted code blocks.** Markdown files from coding workflows are full of code snippets. They render with proper highlighting, just like you'd expect.

**Word count.** Handy when you're checking document length or comparing verbosity between versions.

**Drag and drop.** No file picker dialogs. Just drag your `.md` or `.mdx` file onto the pane.

**Works via `file://` protocol.** No local server needed. No `python -m http.server`. No `npx serve`. Just a file in your filesystem, opened in Chrome.

## Why MDX matters

MDX — Markdown with JSX — is showing up everywhere. Docusaurus, Next.js docs, Storybook, Astro. If you're working on React-based documentation, your content files are probably `.mdx`. Most lightweight Markdown viewers choke on them or just don't recognize the extension. This one handles both.

## Who is this for

Honestly? Anyone who works with Markdown regularly and wants a viewer that stays out of the way. But especially:

- **GenAI power users** who accumulate dozens of `.md` files from Claude Code, ChatGPT exports, Copilot docs
- **Developers** who maintain documentation in Markdown and need quick previews
- **Multilingual teams** who work with RTL languages and are tired of broken rendering
- **Anyone** who just wants to view a Markdown file without installing something

## Try it

It's open source, MIT licensed, and free. You can use it right now:

- **GitHub Pages demo:** [https://samueldratwa-TG.github.io/MDreader/](https://samueldratwa-TG.github.io/MDreader/)
- **GitHub repo:** [https://github.com/samueldratwa-TG/MDreader](https://github.com/samueldratwa-TG/MDreader)

Download `index.html`, put it anywhere, double-click. That's the whole setup.

---

*Built with genuine need and a little help from Claude Code. If you find it useful, a star on GitHub is always appreciated.*

---

<div dir="rtl" align="right">

# בניתי כלי לקרוא Markdown — כי ה-AI שלי לא מפסיק לכתוב

## בקצרה (TL;DR)

מי שעובד עם Claude Code, ChatGPT או כלי GenAI אחרים יודע: הכל מתנהל ב-Markdown. קבצי זיכרון, מפרטים, תיעוד, לוגים — הכל `.md`. חיפשתי כלי פשוט לצפות בקבצים האלה rendered, עם תמיכה ב-RTL והשוואה צד-בצד, בלי להתקין כלום. לא מצאתי. אז בניתי אחד. קובץ HTML בודד, ~188KB, פותחים בדאבל-קליק. קוד פתוח, חינם, MIT.

---

## הבעיה: מבול של Markdown

אם אתם עובדים עם Claude Code (ה-CLI של Anthropic), אתם יודעים שהחיים שלכם הם Markdown. יש `CLAUDE.md` שמגדיר את ההקשר של הפרויקט. יש קבצי זיכרון ב-`.claude/` שהכלי כותב ומעדכן. יש מפרטים שאתם כותבים בעברית ומתרגמים לאנגלית. יש changelogs, יש prompts שמורים, יש תיעוד שנוצר אוטומטית.

וזה לא רק Claude. כל כלי ה-GenAI עובדים ככה — ChatGPT, Gemini, Copilot — כולם "מדברים" ב-Markdown. זה פורמט התקשורת של עידן ה-AI. ולאחרונה גם MDX (Markdown עם קומפוננטות React) הפך לסטנדרט בתיעוד מודרני — Docusaurus, Next.js, React docs — כולם MDX.

הבעיה? קבצי `.md` גולמיים נראים נורא. כותרות עם `###`, קישורים עם סוגריים מרובעים, בלוקים של קוד עטופים ב-backticks. לפעמים צריך פשוט לראות את המסמך rendered — כמו שהוא נראה ב-GitHub — בלי לדחוף אותו ל-GitHub.

ויש לי עוד בעיה: אני עובד הרבה בעברית. מתרגם מסמכים, כותב מפרטים בעברית, משווה בין גרסאות עברית/אנגלית. רוב הכלים שמצאתי לא תומכים ב-RTL בצורה נורמלית.

## מה ניסיתי (ולמה זה לא עבד)

- **VS Code Preview** — עובד, אבל צריך לפתוח VS Code. ואי אפשר להשוות שני קבצים rendered.
- **Typora / Obsidian** — כלים מעולים, אבל צריך להתקין. ואני רוצה משהו שאני פשוט פותח.
- **grip (GitHub Readme Instant Preview)** — צריך Python, שרת, ו-API token של GitHub. רציני?
- **כלים אונליין** — דורשים העלאה לענן. לקבצים פנימיים? לא, תודה.
- **Marked.js demo / Dillinger** — אונליין בלבד, בלי RTL, בלי השוואה.

מה שרציתי: קובץ אחד, בלי התקנה, בלי שרת, בלי אינטרנט. פותח בדאבל-קליק, גורר לתוכו markdown, רואה תוצאה יפה. עם RTL. עם השוואה.

## אז בניתי אחד

והאירוניה? בניתי את זה עם Claude Code עצמו. הכלי שיוצר את ההרים של Markdown — עזר לי לבנות כלי לקרוא אותם. סשן אחד, כמה שעות, והתוצאה: **MD/MDX Viewer**.

### מה בפנים:

- **קובץ HTML בודד** — ~188KB, הכל inline. `marked.js` לפרסור Markdown, `highlight.js` להדגשת קוד, CSS מוטמע. אפס תלויות חיצוניות.
- **פאנל כפול להשוואה** — גוררים קובץ לצד שמאל, קובץ אחר לצד ימין. מושלם לתרגומים (עברית/אנגלית), גרסאות (לפני/אחרי), או השוואת מפרטים.
- **RTL/LTR לכל פאנל בנפרד** — כפתור toggle שמחליף כיוון טקסט. הכרחי למי שעובד עם תוכן בעברית ובאנגלית במקביל.
- **סנכרון גלילה** — גוללים בפאנל אחד, השני זז איתו. קריטי להשוואה מקבילה.
- **ערכת צבעים כהה/בהירה** — כי מי לא צריך dark mode ב-2026.
- **הדגשת קוד** — syntax highlighting אוטומטי לבלוקים של קוד.
- **ספירת מילים** — שימושי כשיש מגבלות אורך.
- **Drag & Drop** — גוררים קובץ ישירות לחלון הדפדפן. זהו.

### מה אין בפנים:

- שרת
- npm install
- Electron
- חשבון משתמש
- ענן
- טלמטריה

הכל רץ דרך `file://` בדפדפן. Chrome, Edge, Firefox — פשוט פותחים את הקובץ.

## למי זה מתאים?

- **מפתחים שעובדים עם Claude Code** — לצפות ב-CLAUDE.md, קבצי זיכרון, מפרטים
- **מפתחים שעובדים עם כלי GenAI** — לקרוא פלט, השוואת גרסאות, בדיקת תיעוד
- **כותבי תוכן טכני** — לבדוק איך markdown ייראה rendered
- **דוברי עברית** — סוף סוף כלי שמבין RTL בלי patches

## נסו את זה

- **GitHub:** [קישור לריפו](https://github.com/samueldratwa-TG/MDreader)
- **הורדה ישירה:** [index.html](https://github.com/samueldratwa-TG/MDreader/releases/latest)
- **רישיון:** MIT — קחו, שנו, עשו מה שבא לכם

פשוט הורידו את `index.html`, פתחו בדאבל-קליק, גררו קובץ `.md` — וזהו. בלי התקנה, בלי שרת, בלי סיפורים.

---

*אם הכלי עזר לכם — תנו כוכב ב-GitHub. אם חסר לכם פיצ'ר — פתחו issue. אם יש לכם כלי markdown אחר שאתם אוהבים — ספרו לי, תמיד שמח ללמוד על כלים חדשים.*

</div>
