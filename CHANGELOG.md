# Changelog

Versions follow [semver](https://semver.org/). See [README.md](README.md#versioning).

## 1.3.0 · 2026-09-26

### Fixed
- Stopping a session early now reports the cards actually seen. Before, stopping at
  card 3 of 10 said "You practiced 10 words".
- The done screen's two-line message now shows on two lines.

### Changed
- Words that are slurs or sexual terms (for example FAG, SEX, TIT) can no longer
  appear. They're listed in `BLOCKED` in `index.html`.
- Soft-C words (C before E or I, like CEN or CIP) no longer appear.
- Words ending in R (BAR, HER, FUR) no longer appear, so every card is a short vowel.
- **Back** is disabled on the first card.
- The version footer uses semver and ISO dates.

### Internal
- Simplified `startSession()` and removed the redundant `stopSession()` wrapper.
- The title is a real `<h1>`, and the page has a meta description.
- Added README and CHANGELOG.

## 1.2 · 2026-04-08

- Added a **Stop** button, **Pause**/**Resume** in timed mode and a version footer.
- Fixed a card count bug.

## 1.0 · 2026-04-08

- First release: CVC word flashcards with card-count and timed modes.
