```dataviewjs
// 5 random notes from #read-watch-later with tight bullet spacing
const taggedNotes = dv.pages("#read-watch-later").array();
const shuffled = taggedNotes.sort(() => 0.5 - Math.random());
const selected = shuffled.slice(0, 5);

dv.header(3, "Random Picks from #read-watch-later");

dv.paragraph(selected.map(note => `• [[${note.file.name}]]`).join("<br>"));
```