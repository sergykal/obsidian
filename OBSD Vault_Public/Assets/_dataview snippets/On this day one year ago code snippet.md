```dataviewjs
const oneYearAgo = window.moment().subtract(1, 'year').startOf('day');
dv.header(1, "On this day…");

const results = dv.pages()
  .where(p => p.file.ctime && window.moment(p.file.ctime).startOf('day').isSame(oneYearAgo));

if (results.length === 0) {
  dv.paragraph("No notes were created on this day one year ago.");
} else {
  results.forEach(p =>
    dv.paragraph(`- [${p.file.name}](${p.file.path}) (Created: ${window.moment(p.file.ctime).format("YYYY-MM-DD")})`)
  );
}


```