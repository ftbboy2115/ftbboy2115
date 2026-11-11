# Issue tracker: Local Markdown (marketplace-agent)

Issues, specs and wayfinder maps for this project live as markdown files in `marketplace-agent/wayfinder/`. Nothing goes in the repo root.

## Conventions

- One effort per directory: `marketplace-agent/wayfinder/<effort-slug>/`
- A spec is `marketplace-agent/wayfinder/<effort-slug>/spec.md`
- One file per ticket at `marketplace-agent/wayfinder/<effort-slug>/issues/<NN>-<slug>.md`, numbered from `01`, never a single combined tickets file
- Comments and conversation history append to the bottom of the file under a `## Comments` heading

## When a skill says "publish to the issue tracker"

Create a new file under `marketplace-agent/wayfinder/<effort-slug>/` (creating the directory if needed).

## When a skill says "fetch the relevant ticket"

Read the file at the referenced path. The user will normally pass the path or the ticket number directly.

## Wayfinding operations

Used by `/wayfinder`. The **map** is a file with one **child** file per ticket.

- **Map**: `marketplace-agent/wayfinder/<effort>/map.md` (the Destination / Notes / Decisions-so-far / Not-yet-specified / Out-of-scope body).
- **Child ticket**: `marketplace-agent/wayfinder/<effort>/issues/NN-<slug>.md`, numbered from `01`, with the question in the body. A `Type:` line records the ticket type (`research`/`prototype`/`grilling`/`task`); a `Status:` line records `open`/`claimed`/`resolved`.
- **Blocking**: a `Blocked by: NN, NN` line near the top. A ticket is unblocked when every file it lists is `resolved`.
- **Frontier**: scan `issues/` for files that are open, unblocked, and unclaimed; first by number wins.
- **Claim**: set `Status: claimed` and save before any work.
- **Resolve**: append the answer under an `## Answer` heading, set `Status: resolved`, then append a context pointer (gist + link) to the map's Decisions-so-far in `map.md`.
- **Research branches**: research findings may go on a throwaway `research/<name>` branch as the skill says, but also copy the findings file into `marketplace-agent/wayfinder/<effort>/research/` so the phone/GitHub view has them on the working branch.
