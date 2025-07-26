---
tags:
  - habits
  - journal
  - wellness/lifestyle
  - year/2025
  - log
aliases:
  - habits
ref: "[[My Properties Legend]]"
---
```dataviewjs

const trackerData = {
    year: 2025,
    entries: [],
    separateMonths: true,
    heatmapTitle: "Mood Tracker",
    heatmapSubtitle: "Tracking my daily mood. Value 1-5.",
    colorScheme: {
        paletteName: "Serge 1", 
        
    },

    // OPTIONAL: If you want to define your own intensity start/end values.
    // Use this if you want to have a custom intensity scale.
    // E.g. if you want to track book reading progress only from 30 minutes to 2 hours.
    defaultEntryIntensity: 3,
    intensityScaleStart: 1,
    intensityScaleEnd: 5
}

// Path to the folder with notes
const PATH_TO_YOUR_FOLDER = "JOURNAL/Daily Notes";
// Name of the parameter you want to see on this heatmap
const PARAMETER_NAME = 'mood';

// You need dataviewjs plugin to get information from your pages
for(let page of dv.pages(`"${PATH_TO_YOUR_FOLDER}"`).where((p) => p[PARAMETER_NAME])){
    trackerData.entries.push({
        date: page.file.name,
        intensity: page[PARAMETER_NAME],
        content: await dv.span(`[](${page.file.name})`)
    });
}

renderHeatmapTracker(this.container, trackerData);


  
```
***

```dataviewjs
// Update this object
const trackerData = {
    year: 2025,
    entries: [],
    separateMonths: true,
    heatmapTitle: "Reading Tracker",
    heatmapSubtitle: "Tracking my reading habits.",

}





// Path to the folder with notes
const PATH_TO_YOUR_FOLDER = "JOURNAL/Daily Notes";
// Name of the parameter you want to see on this heatmap
const PARAMETER_NAME = 'reading';

// You need dataviewjs plugin to get information from your pages
for(let page of dv.pages(`"${PATH_TO_YOUR_FOLDER}"`).where((p) => p[PARAMETER_NAME])){
    trackerData.entries.push({
        date: page.file.name,
        intensity: page[PARAMETER_NAME],
        content: await dv.span(`[](${page.file.name})`)
    });
}


renderHeatmapTracker(this.container, trackerData);
```
---

```dataviewjs
// Update this object
const trackerData = {
    year: 2025,
    entries: [],
    separateMonths: true,
    heatmapTitle: "Challenge Tracker",
    heatmapSubtitle: "Workouts",
}

// Path to the folder with notes
const PATH_TO_YOUR_FOLDER = "JOURNAL/Daily Notes";
// Name of the parameter you want to see on this heatmap
const PARAMETER_NAME = 'challenge';

// You need dataviewjs plugin to get information from your pages
for(let page of dv.pages(`"${PATH_TO_YOUR_FOLDER}"`).where((p) => p[PARAMETER_NAME])){
    trackerData.entries.push({
        date: page.file.name,
        intensity: page[PARAMETER_NAME],
        content: await dv.span(`[](${page.file.name})`)
    });
}

renderHeatmapTracker(this.container, trackerData);
```