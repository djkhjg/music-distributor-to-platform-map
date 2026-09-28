# Music Distributor to Platform Map

A sourced dataset showing which music distributors deliver to which streaming services, download stores, and other music platforms.

**[View the interactive table](https://djkhjg.github.io/music-distributor-to-platform-map/)**

## Dataset

[distributor-platforms.json](distributor-platforms.json) contains:

- **providers** — platforms, keyed by stable IDs, with names, aliases, descriptions, groups, and links.
- **distributors** — distributors and their platform compatibility records, including status, notes, sources, and review dates.
- **sourceMetadata** — source dates and access details.

Missing relationships mean **unknown**, not unsupported. A release appearing on a platform does not necessarily mean its distributor delivered it there; it may have been uploaded separately or supplied by another distributor.

## Statuses

| Symbol | Status | Meaning |
| --- | --- | --- |
| ✓ | yes | Evidence supports delivery. |
| ✕ | no | Unsupported; historical availability is unspecified. |
| ∅ | never | Explicit evidence that delivery has never been supported. |
| ? | maybe | Qualified, conflicting, or uncertain evidence. |
| ■ | ended | Previously supported; delivery has ended. |
| Ⅱ | paused | New delivery is temporarily suspended. |
| ~ | unknown | No conclusion recorded. |

Ended and paused records include an **endedAt** or **pausedAt** date, or null when unknown. Earlier releases may still exist on the platform; notes explain any known catalog removals. **verified** is the evidence review date, not the source publication date or a guarantee of current support.

## HTML page

[distributor-platforms.html](distributor-platforms.html) loads the JSON directly from this repository. It offers search, group filters, sorting, and notes with clickable sources on hover or keyboard focus. The small **Load local file** button lets you preview another JSON file without uploading it. It does not edit or save the dataset.

Platforms marked **active: false** are hidden by default; choose **Include inactive** to display them. This flag controls visibility, not whether a service has shut down.

[index.html](index.html) opens the table from the GitHub Pages homepage. No build step or backend is required.

## Updating the data

Edit the JSON and commit it to the repository. Include source URLs and concise notes for new claims, and preserve the distinction between unsupported, never supported, and ended delivery. Absence from a partner list alone is not proof of non-support.

An entity's **source** is its own published partner list. Relationship **sources** can include either party's list and supporting evidence.
