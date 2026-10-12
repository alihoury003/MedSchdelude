# Ali’s MED II Command Center

A self-contained, editable planning site for MED II, study, prayer, training, research, Scouts, family time, Barça fixtures, and the White Coat Ceremony. It is plain HTML/CSS/JavaScript—no build framework, account, backend, or external CSS/JavaScript dependency is needed to use the published site.

## Publish with GitHub Pages

The ready-to-publish file is `index.html`.

1. Create a GitHub repository and upload the contents of this folder.
2. In the repository, open **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Choose the branch (usually `main`) and the folder containing `index.html`:
   - select `/(root)` if `index.html` is at the repository root; or
   - select `/docs` if you copied the site into a `docs/` folder.
5. Save and open the Pages URL shown by GitHub after deployment completes.

You can also test it locally by running `python3 -m http.server 8000` in this folder and opening `http://localhost:8000`.

## What is included

- UOB MED II timetable, seeded with 187 parsed schedule entries and the manually checked White Coat Ceremony entry.
- Editable calendar, recurring routine anchors, event import/export, local JSON backup/restore, and a private-on-this-device workflow.
- Offline prayer-time estimates for Baabda using `Asia/Beirut` time-zone rules, editable calculation settings, and date-specific local-mosque Athān overrides. Friday Jumu’ah is scheduled 30 minutes after Dhuhr Athān, with 30 minutes before and after prayer.
- The immediate ENRP504 exam sprint, the editable Reproductive B&B checklist, an Anki counter, UWorld block/review tracking, and a focus timer.
- Gym, Scouts, family, meals, literature-review and business anchors; gradual wake-time controls; exam and ceremony countdowns.
- A small rolling Barça fixture seed plus an optional live-sync/import path. Future fixtures may not yet be announced, and kickoff times can change.

## Editing and persistence

- Use the in-app **＋ Add event**, calendar event editing, **Mosque times**, settings, and milestone controls to customize the plan.
- Changes are saved in the current browser’s local storage; they are not uploaded to GitHub or synchronized across devices. Use **Backup** regularly and restore the downloaded JSON on another browser/device.
- Browser data can be removed when site data/cookies are cleared. Keep a backup before clearing it.
- Prayer times are estimates rather than an official mosque timetable. Set a date-specific override when you have the local schedule; the calculation method, Asr convention, commute buffer, and global adjustment are editable in Settings.
- The ESPN seed was collected for the 28-day window starting 12 October 2026. The live sync is a rolling feed check, not a complete season fixture list. Use an official calendar import or manual edit for matches missing from the feed.
- The timetable was transcribed from the supplied UOB PDF. A few dense or merged cells may need manual correction; tap any event to review/edit it.

## Rebuilding after changing the seed data

`index.html` is already built and ready to publish. If you edit the source timetable, match seed, or app template, rebuild the standalone page with Python 3:

```bash
python3 build.py
```

The build script uses only the Python standard library. `index.template.html`, `schedule-data.js`, and `matches-seed.json` are the editable source files; the generated `index.html` is the GitHub Pages entry point.
