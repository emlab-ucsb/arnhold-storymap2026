# Arnhold CSC StoryMap Embeds (2026)

Custom interactive elements for the 2026 StoryMap of the **Arnhold UC Santa Barbara–Conservation International Climate Solutions Collaborative (Arnhold CSC)**, maintained by [emLab](https://emlab.ucsb.edu/) at UC Santa Barbara.

Each folder holds a small, self-contained web page (`index.html`) that is hosted from this repository and embedded into the StoryMap. Together they showcase the Collaborative's conservation work and the students who carry it out as Arnhold Environmental Fellows.

## What's in this repo

| Folder | What it is |
| --- | --- |
| `5images/` | **Blue 5 Species Range Maps.** A scroll-driven section featuring five iconic marine species (green sea turtle, humpback whale, pantropical spotted dolphin, whale shark, and giant manta ray). Scrolling moves through each species and loads its range map from ArcGIS Online. |
| `studentsheadshot/` | **Student Headshot Grid.** A photo grid of Arnhold Fellows. |
| `Gemma/` | **Student Perspective** cards for Gemma Di Rossi and Zachary Scholnick. |
| `MaxwellandVikesh/` | **Student Perspective** cards for Maxwell Pepperdine and Vikesh Dheeriya. |
| `Surayu-lenya/` | **Student Perspective** cards for Sarayu Ramnath, Lenaya Aiden Gonzales, and Hayden Vega. |
| `XaNTHE-Jahat/` | **Student Perspective** cards for Xanthe Vitaz and Jahat Garcia. |

The Student Perspective pages show flip cards: the front has the Fellow's photo, name, and degree, and the back shows a short quote about their experience.

## How the embeds work

Each `index.html` is a standalone page with its styles and scripts built in, so it can be dropped into the StoryMap as an embed by URL. Photos are stored next to the page that uses them (in `photos/` or `student_photos/`). Backgrounds are transparent so the embeds blend into the StoryMap's layout.

The species maps use the ArcGIS Maps SDK for JavaScript and pull each range map from ArcGIS Online by its web map ID.

## Making updates

**Editing a Student Perspective block.** Open the folder's `index.html` and find the `STUDENTS` list near the bottom of the file. Each entry has a `name`, `degree`, `quote`, and `img`. To add a photo, put the image in that folder's `student_photos/` and set `img` to its path (for example, `"student_photos/first-last.jpg"`), or set `img` to `null` to show the Fellow's initials instead. Keep quotes within the character limit noted at the top of the list so the back of each card doesn't need to scroll.

**Adding a new Student Perspective block.** Copy an existing student folder, rename it, swap in the new Fellows' entries and photos, and embed the new folder's URL in the StoryMap.

**Editing the species maps.** In `5images/index.html`, find the `SPECIES` list. Each species has a `name`, a photo (`img`), and a `webmapId`, which is the ID of its web map in ArcGIS Online.

After committing changes to `main`, the live embeds update automatically (allow a few minutes), so there's no need to change anything in the StoryMap unless a folder is renamed or added.

## Hosting

The pages are served with GitHub Pages. Each embed's URL follows this pattern:

```
https://emlab-ucsb.github.io/arnhold-storymap2026/<folder-name>/
```

Renaming a folder or the repository changes these URLs, so update the matching embeds in the StoryMap whenever that happens.

## Credits

Species photos are from [Unsplash](https://unsplash.com/). Student photos and quotes are used with permission of the Arnhold Fellows.
