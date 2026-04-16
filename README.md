# MD/MDX Viewer

<!-- GitHub Pages badge placeholder — update URL after enabling Pages -->
[![GitHub Pages](https://img.shields.io/badge/demo-GitHub%20Pages-blue?logo=github)](https://samueldratwa-TG.github.io/MDreader/)

A single self-contained HTML file (~188 KB) that renders Markdown and MDX files in the browser. No install, no server, no dependencies. Works fully offline via `file://`.

---

## Features

| Feature | Details |
|---|---|
| File formats | `.md` and `.mdx` |
| View modes | Single pane or dual pane (side by side) |
| File loading | Drag & drop or click-to-browse; drop/select two files at once to open both side by side |
| Reload | Re-read open files from disk after external edits (&#8635; Reload button) |
| Text direction | Independent RTL / LTR toggle per pane |
| Theme | Global dark / light mode (persisted in `localStorage`) |
| Pane resizing | Draggable divider; double-click to reset 50/50 |
| Scroll sync | Synchronized scrolling between panes (toggle on/off) |
| Word count | Displayed per pane |
| Syntax highlighting | JavaScript, Python, CSS, and many more |
| MDX support | JSX tags rendered as styled labels instead of broken HTML |
| Close per pane | Unload a file without affecting the other pane |
| Responsive | Stacks vertically on narrow screens |
| Offline | Zero external requests; works via `file://` in Chrome |
| Embedded libraries | marked.js v15, highlight.js v11.9 |

## Quick Start

1. **Get the file** — download `index.html` or clone this repo.
2. **Open in Chrome** — double-click the file or drag it into the browser.
3. **Load a file** — drop an `.md` or `.mdx` file on the drop zone, or click to browse.
4. **Side-by-side** — drop or select **two files at once** and both panes open instantly. Or drop one at a time — a second drop zone appears automatically.
5. **Reload** — edited the files externally? Click **↻ Reload** in the toolbar to re-read both from disk without re-dropping.
6. **RTL / LTR** — click the direction button on each pane independently.
7. **Theme** — toggle dark/light mode with the button at the top-left corner.
8. **Scroll Sync** — in dual-pane mode, click "Scroll Sync" to lock both panes together.
9. **Resize panes** — drag the divider between panes; double-click it to reset to 50/50.
10. **Close a file** — click the **✕** button on the pane.

## Use Cases

- Reviewing Markdown documentation offline
- Comparing two versions of the same document side by side
- Reading Hebrew/Arabic Markdown files with proper RTL rendering
- Previewing MDX content without a build step

## GitHub Pages

This viewer is also available as a hosted page — no download needed. Visit the badge link at the top of this README (once GitHub Pages is enabled on the repo).

To enable it yourself: **Settings → Pages → Source → Deploy from a branch → `main` / `/ (root)`**.

## Technical Notes

- Everything is inlined in a single HTML file — no external CSS, JS, or font requests.
- `marked.js` handles Markdown parsing; `highlight.js` handles syntax highlighting.
- MDX JSX tags (`<Component />`) are detected and replaced with styled `<span>` labels before parsing so they don't break the HTML output.
- Theme preference is saved to `localStorage` and restored on next open.

## License

Use freely. No restrictions.

---

<div dir="rtl" align="right">

# MD/MDX Viewer — מציג קבצי מרקדאון

<!-- תג GitHub Pages — עדכנו את הכתובת אחרי הפעלת Pages -->
[![GitHub Pages](https://img.shields.io/badge/demo-GitHub%20Pages-blue?logo=github)](https://samueldratwa-TG.github.io/MDreader/)

קובץ HTML יחיד ועצמאי (~188 KB) שמציג קבצי Markdown ו-MDX בדפדפן. בלי התקנה, בלי שרת, בלי תלויות. עובד לגמרי אופליין דרך `file://`.

---

## תכונות

| תכונה | פרטים |
|---|---|
| פורמטים | `.md` ו-`.mdx` |
| מצבי תצוגה | חלונית יחידה או שתי חלוניות זו לצד זו |
| טעינת קבצים | גרירה ושחרור (drag & drop) או לחיצה לבחירת קובץ; ניתן לגרור/לבחור שני קבצים בבת אחת |
| טעינה מחדש | קריאה מחדש של הקבצים הפתוחים מהדיסק אחרי עריכה חיצונית (כפתור ↻ Reload) |
| כיוון טקסט | כפתור RTL / LTR עצמאי לכל חלונית |
| ערכת נושא | מצב כהה / בהיר (נשמר ב-`localStorage`) |
| שינוי גודל חלוניות | מחיצה נגררת; לחיצה כפולה מאפסת ל-50/50 |
| סנכרון גלילה | גלילה מסונכרנת בין שתי החלוניות (ניתן להפעלה/כיבוי) |
| ספירת מילים | מוצגת לכל חלונית |
| הדגשת תחביר | JavaScript, Python, CSS ועוד שפות רבות |
| תמיכת MDX | תגיות JSX מוצגות כתוויות מעוצבות במקום HTML שבור |
| סגירה לכל חלונית | פריקת קובץ בלי להשפיע על החלונית השנייה |
| רספונסיבי | עובר לתצוגה אנכית במסכים צרים |
| אופליין | אפס בקשות חיצוניות; עובד דרך `file://` ב-Chrome |
| ספריות מוטמעות | marked.js v15, highlight.js v11.9 |

## התחלה מהירה

1. **הורידו את הקובץ** — הורידו את `index.html` או שכפלו את הריפו.
2. **פתחו ב-Chrome** — לחצו פעמיים על הקובץ או גררו אותו לדפדפן.
3. **טענו קובץ** — גררו קובץ `.md` או `.mdx` לאזור הגרירה, או לחצו כדי לבחור קובץ.
4. **תצוגה מקבילה** — גררו או בחרו **שני קבצים בבת אחת** ושתי החלוניות נפתחות מיד. אפשר גם לגרור אחד בכל פעם — אזור גרירה שני מופיע אוטומטית.
5. **טעינה מחדש** — ערכתם את הקבצים בחוץ? לחצו על **↻ Reload** בסרגל הכלים כדי לקרוא את שניהם מחדש מהדיסק בלי לגרור שוב.
6. **RTL / LTR** — לחצו על כפתור הכיוון בכל חלונית בנפרד.
7. **ערכת נושא** — החליפו בין מצב כהה לבהיר עם הכפתור בפינה השמאלית-עליונה.
8. **סנכרון גלילה** — במצב חלונית כפולה, לחצו על "Scroll Sync" לנעילת שתי החלוניות יחד.
9. **שינוי גודל** — גררו את המחיצה בין החלוניות; לחצו עליה פעמיים לאיפוס ל-50/50.
10. **סגירת קובץ** — לחצו על כפתור **✕** בחלונית.

## שימושים לדוגמה

- קריאת תיעוד Markdown אופליין
- השוואת שתי גרסאות של אותו מסמך זו לצד זו
- קריאת קבצי Markdown בעברית/ערבית עם כיוון RTL תקין
- תצוגה מקדימה של תוכן MDX בלי צורך בבנייה (build)

## GitHub Pages

המציג זמין גם כאתר מתארח — בלי צורך בהורדה. בקרו בקישור התג בראש העמוד (אחרי שתפעילו GitHub Pages בריפו).

להפעלה: **Settings → Pages → Source → Deploy from a branch → `main` / `/ (root)`**.

## הערות טכניות

- הכל מוטמע בקובץ HTML יחיד — בלי בקשות חיצוניות ל-CSS, JS או פונטים.
- `marked.js` אחראי על פענוח Markdown; `highlight.js` אחראי על הדגשת תחביר.
- תגיות JSX של MDX (כמו `<Component />`) מזוהות ומוחלפות בתוויות `<span>` מעוצבות לפני הפענוח, כדי שלא ישברו את ה-HTML.
- העדפת ערכת הנושא נשמרת ב-`localStorage` ומשוחזרת בפתיחה הבאה.

## רישיון

שימוש חופשי. ללא הגבלות.

</div>
