# IntentOne event day

The single-page app for the IntentOne company event day: hackathon submissions, the best-ideas box, the info packs, and the judged shortlist.

**Live site:** https://georgefoster-blip.github.io/intentone-event-day/

## How it works

The app is one static `index.html` served by GitHub Pages. There is no backend: submissions are GitHub issues in this repository.

- **Submitting.** The forms on the page open a pre-filled GitHub issue form; the submitter presses the confirm button on GitHub. They must be signed in to GitHub. Facilitators can file entries on behalf of anyone without an account.
- **Listing.** The page reads open issues by label through the public GitHub API: `hackathon-submission` for hackathon entries, `best-idea` for ideas, `shortlisted` for the judged shortlist.
- **Shortlisting.** The judging mechanism is intentionally not wired in yet. When it runs (an AI judging pass over the submissions), it adds the `shortlisted` label to the chosen entries and posts its reasoning as a comment; the shortlist page picks them up automatically. Nothing in the app needs to change to plug this in.

## Editing the info packs

The pack content is plain HTML in `index.html` under the `view-packs` section (and the hackathon brief under `view-hackathon`). Each placeholder block marked "to be filled" is replaced with the real content when it is ready. Push to `main` and Pages redeploys.

## Brand

The page follows the Intent genome brand. `css/tokens.css` and `css/genome-light.css` are vendored **verbatim** from `@intenthq/design-system` v3.17.3 (the sanctioned no-build route) — do not edit them; to upgrade, replace both files from the versioned design-system host and update the version noted in `index.html`. All page styles reference `--io-*` roles only.

## Configuration

Repository coordinates live in the `CFG` object at the top of the script in `index.html`. If the repo moves, update `owner` and `repo` there.
