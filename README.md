# PyGame Zero Coach

A Codio Custom Assistant (Virtual Coach) for middle school students making games with [Pygame Zero](https://pygame-zero.readthedocs.io/).

## What it does

- Reads the student's open files and the current guide page before every answer, so it always sees their latest code.
- Includes a Pygame Zero reference in its instructions: actors, screen drawing, collisions, keyboard input and `pgzrun`.
- Warns students that sound and music don't work in Codio.
- Diagnoses bugs directly and coaches design questions step by step, without writing full games.
- Tells students how to run their game in Codio: **▶ Run**, then **🖥 Open Graphics**.

One `index.js` plus `metadata.json`, with no build step and no dependencies. Release tags in this repo have no `v` prefix (for example, `2.5.0`).

## Using it in Codio

1. In Codio, go to **Organization > Extensions**, click **Add extension**, and paste this repository's URL. You need to be an organization owner.
2. Choose the coach in the [Virtual Coach settings](https://docs.codio.com/instructors/setupcourses/assignment-settings/virtual-coach.html) for a course or assignment.
3. After a new release, click **Check for Updates** on the Extensions page. Students can type `version` in the coach to see which version is running.

Every change to `index.js` or `metadata.json` needs a new GitHub release, with a tag that matches the `VERSION` constant in `index.js`.

## Session log

Each coach session adds a short summary to a hidden `.coach-log.json` file in the student's workspace: when it started and ended, the coach version, how many questions were asked, and the questions themselves (up to 50, each cut to 300 characters). Codio's own coach-log export leaves the student's question blank for message-based coaches like this one, so this file is the only record of what students asked. It's never sent to the model, and logging can't break the coach.

## Development

```bash
node --check index.js
```
