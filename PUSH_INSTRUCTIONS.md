# Push instructions for another Cowork / Claude session

## Goal
Push the finished static site in `D:\project temo\AWSTalk` to this GitHub repository, on branch `main`:

    https://github.com/pinological/Awsmeet-presentation-slide3d-edge-to-cloud-.git

Owner: `pinological`. Repo name: `Awsmeet-presentation-slide3d-edge-to-cloud-` (it ends with a hyphen, keep it).

## Current state
- The folder is a plain static site: `index.html`, `app.js`, `README.md`, `fonts/`, `img/`. No build step.
- A local git repo already exists in the folder with one commit on `main` and `origin` set to the URL above.
- Nothing has been pushed yet. A previous session could not push because its GitHub account was not linked,
  and the sandbox shell blocks `git push` ("Cowork blocked this request").
- Two harmless leftover files may sit in `.git`: `stale-HEAD.lock` and `objects/stale-maintenance.lock`. Ignore or delete them.

## What you need
1. The folder `D:\project temo\AWSTalk` connected to the session (ask the user to add it if it is not).
2. Write access to the repo, by one of these:
   - the GitHub connector linked in the user's claude.ai Settings, then `add_repo` with `access: "push"`; or
   - a terminal on the user's own computer with git and their GitHub login (the simplest route).

## Steps
### Route A: terminal on the user's computer (recommended)
```
cd "D:\project temo\AWSTalk"
git status
git remote -v
git pull --rebase origin main    # only if the repo already has commits; skip if GitHub says the remote is empty
git push -u origin main
```
If `git status` complains about a `.lock` file, delete the stale lock named in the message, then retry.

### Route B: Claude session with the GitHub connector
1. Call `add_repo` for `pinological/Awsmeet-presentation-slide3d-edge-to-cloud-` with `access: "push"`. Do not pre-check the repo with curl.
2. Clone it into a new empty directory, then copy in everything from `AWSTalk` except the `.git` folder.
3. Commit with a clear message, for example "Edge to Cloud: 3D talk for AWS Student Community Day Kathmandu 2026".
4. Push to `main`. Do not force-push. If the remote already has history, rebase on it first.

## Check it worked
- The repo root on GitHub shows `index.html` at the top level, plus `app.js`, `README.md`, `fonts/`, `img/`.
- `index.html` is NOT inside a subfolder (Netlify and GitHub Pages need it at the root).
- Optional: enable GitHub Pages (Settings, Pages, branch `main`, folder `/ (root)`) or connect the repo to Netlify
  with an empty build command and publish directory `/`.

## Do not
- Do not change the site files. They are final; the QR code on the last slide builds itself from whatever address hosts the page.
- Do not force-push, rewrite history or delete branches.
- Do not commit anything else from the user's machine (keys, tokens, other folders).
- You may leave this `PUSH_INSTRUCTIONS.md` out of the commit, or include it; either is fine.
