# BNTU schedule

A vibecoded offline web app (PWA) for viewing a 2-week period timetable.

## Files

- `schedule.txt`: the data. Edit this file only. The format is described in its first lines.
- `index.html`: the parser and the view.
- `sw.js`: the offline cache.
- `manifest.webmanifest`, `icon-*.png`: the home-screen icon and name.
- `.nojekyll`: an empty file. It tells GitHub Pages to publish the files as they are, without a Jekyll build.

## Put it on GitHub Pages

1. Create a GitHub repository, for example `bntu-schedule`.
2. Push these files to the `main` branch.
3. In the repository, open Settings → Pages. Set Source to "Deploy from a branch", `main`, `/ (root)`.
4. On the phone, open `https://<user>.github.io/bntu-schedule/` in Chrome.
5. Open the Chrome menu and tap "Add to Home screen" (or "Install app").

## Change the schedule

1. Edit `schedule.txt`.
2. Test on the computer: run `python3 -m http.server` in this folder and open `http://localhost:8000`.
3. Push. The phone shows the new data the next time you open the app while it has network access.

If a line has an error, the app shows the line number and the text at the top of the page.

## Use

- The bar with the week and the buttons is at the bottom of the screen, so the thumb reaches it.
- `неделя N` at the left of the bar shows the number (1 or 2) of the week on the screen. In the grid, it is the number of the first week.
- The `‹` and `›` arrows, or a swipe left or right, move one week back or forward.
- The date range button (Monday to Sunday) opens a date picker. Pick any day to see its week.
- The range button has a bold border when the page shows a week other than the current one. On Saturday and Sunday, the next week counts as the current one.
- When you open the app again, it goes back to the current week.
- The button at the right switches the layout. It shows the name of the other layout: "сетка" or "список". The app remembers your choice.
- In both layouts, tap a class to see the end time, the full subject name, and the teacher. Tap again to hide the details.
- A building number in bold means that the class is in a different building from the previous class of the day.
- Blue marks only today, the current class and the next class. The types have their own colors: green for "пр", red for "лаб", purple for "КП", gray for "лек" and for no type. People with the common types of color blindness can also tell these colors apart.

### The list ("список")

- One row for each class: start time, type, subject, room, teacher's surname.
- A day header shows the start of the first class and the end of the last class.
- When the app opens, it scrolls to today. After the last class of today, it scrolls to the next day with classes.
- Before the first class of today and during a break, a blue line above the next class shows the time to wait.

### The grid ("сетка")

- Four weeks: the week from the date range and the 3 weeks after it. Slots are rows, days are columns.
- A week has no rows for the free slots before its first class and after its last class.
- The header row of a week shows the week number at the left, for example "нед. 1", and then the days.
- When you scroll, the header row of the week on the screen stays at the top.
- A cell shows the subject and the room. The color of the left edge shows the type.
- Today's column has a blue tint. Past days are pale. The current class has a blue frame. The next class has a blue name.
- The details of a tapped class show above the bar.

### Teacher names

- A class line in `schedule.txt` has only the teacher's surname.
- A `prof` line gives the rest of the name: `prof Дубовская Елена Михайловна`, or the initials if you do not know the name.
- The rows show the surname. The details show the surname and the text from the `prof` line.
