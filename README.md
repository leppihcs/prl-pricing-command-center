# PRL Pricing Command Center

Live, collaborative HTML document. Source of truth: GitHub. Team edits via StackBlitz. Live view-only URL served by GitHub Pages.

## URLs (fill in after setup)

- **Live site (view-only)**: _paste GitHub Pages URL here_
- **Team edit link (StackBlitz)**: _paste StackBlitz URL here — share this with teammates_
- **GitHub repo**: _paste repo URL here_

## How updates flow

### When the team edits live (StackBlitz)

1. Teammates open the StackBlitz link, sign in with GitHub (free, one-time).
2. Edit `index.html` together in real time (multiplayer cursors).
3. When done, someone clicks **Source Control → Commit & Push** in StackBlitz.
4. GitHub updates → GitHub Pages redeploys (~30s) → live site reflects the change.

### When Claude Code + owner edit locally

1. `git pull origin main` — grab any StackBlitz commits first.
2. Edit `index.html` (Claude Code does this with targeted edits).
3. `git add index.html && git commit -m "describe the change"`.
4. `git push origin main` → GitHub → Pages redeploys → StackBlitz editors can pull to refresh.

## Version history

- **GitHub commits** — every push is a durable snapshot. `git log` browses history; `git checkout <sha> -- index.html` restores a past version locally; `git revert <sha>` undoes a bad change.
- **StackBlitz autosave** — protects in-flight edits between commits (so a closed tab doesn't lose unsaved work).

## Guardrails

- Don't reformat / beautify `index.html` — it's ~30k lines with inline JS; reformatting risks breaking it.
- Don't force-push to `main` without coordinating — that can erase teammate commits.
- Don't commit credentials, tokens, or anything from `.env` files.
