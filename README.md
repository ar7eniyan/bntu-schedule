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

- `неделя N` at the left shows the number (1 or 2) of the week on the screen.
- The `‹` and `›` arrows, or a swipe left or right, move one week back or forward.
- The date range button (Monday to Sunday) opens a date picker. Pick any day to see its week.
- The range button has a bold border when the page shows a week other than the current one. On Saturday and Sunday, the next week counts as the current one.
- When you open the app again, it goes back to the current week.
- The button at the right switches the row layout. It shows the name of the other layout: "подробно" (two lines per class, full names) or "кратко" (one line per class). The app remembers your choice.
- In the one-line layout, tap a row to see the end time, the full subject name, and the teacher.
