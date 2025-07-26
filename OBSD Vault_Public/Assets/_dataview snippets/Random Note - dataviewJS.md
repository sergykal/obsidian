```dataviewjs
const folder = "FILING CABINET";
const pages = dv.pages(`"${folder}"`).where(p => !p.file.name.startsWith("_"));

if (pages.length > 0) {
    const randomPage = pages[Math.floor(Math.random() * pages.length)];
    dv.paragraph(`**Random Note:** [[${randomPage.file.name}]]`);
} else {
    dv.paragraph("No notes found in the Filing Cabinet.");
}
```