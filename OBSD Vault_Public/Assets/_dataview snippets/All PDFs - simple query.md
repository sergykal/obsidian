---
tags:
---
```dataviewjs
const pdfFiles = app.vault.getFiles()
  .filter(file => file.extension === 'pdf')
  .sort((a, b) => a.name.localeCompare(b.name));

let html = `<ol style="padding-left: 1.5em;">`;
pdfFiles.forEach(file => {
  const encodedPath = file.path.replace(/"/g, '&quot;');
  const safeName = file.name.replace(/</g, '&lt;').replace(/>/g, '&gt;');

  html += `<li><a href="#" onclick="app.workspace.openLinkText('${encodedPath}', '${encodedPath}', false); return false;">${safeName}</a></li>`;
});
html += `</ol>`;

const container = dv.container;
container.innerHTML = html;
```