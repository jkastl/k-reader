# Word Flashcards

Flashcards for early readers practicing simple three-letter words: consonant, vowel,
consonant (CVC), like **cat**, **fox** and **sun**.

**[jkastl.github.io/k-reader](https://jkastl.github.io/k-reader/)**

One file, no build step, no dependencies, no network calls. The whole app is
[`index.html`](index.html), served by GitHub Pages from `main`.

## Using it

Pick a mode, then tap **Let's Go!**

- **Number of Cards**: a fixed deck of 1–100 cards. The progress bar fills as you go,
  and the last card's button says **Finish**.
- **By Time**: flip cards for 1–30 minutes. **Pause** stops the clock, and **Next**
  starts it again. The timer turns red in the last 10 seconds.

**Back** and **Next** move between cards, and **Stop** ends the session early. The
done screen counts the cards the reader actually saw.

Consonants are purple and the vowel is red, so the reader can spot the vowel sound.

### Keyboard

| Key | Cards screen |
| --- | --- |
| → , Space or Enter | Next (resumes the timer if paused) |
| ← | Back |
| P | Pause / Resume (timed mode) |
| Esc | Stop |

Enter starts a session from the setup screen, and Enter or Space on the done screen
goes back to setup. A button that has keyboard focus handles its own Enter and Space.

## Words

Words are generated at random, not drawn from a dictionary, so many are pseudo-words
like **wel** or **dop**. That's deliberate: reading a word you've never seen is how
phonics practice checks for decoding rather than memorized sight words.

Each card follows these rules (see the comment block in the `<script>`):

- **First letter:** any consonant except Q and X.
- **Middle letter:** one of A, E, I, O, U, always read as a short vowel.
- **Last letter:** one of B D F G K L M N P S T X. The ending consonants that are
  ambiguous or rare in English are left out. R is left out too, because **bar** and
  **fur** are r-controlled vowels, which phonics usually teaches after short vowels.
- **No soft C:** C never comes before E or I, since **cen** would read as "sen".
- **Blocked words:** anything on the `BLOCKED` list never appears. The list covers
  slurs, sexual terms and misspellings of them. It's stored
  [ROT13](https://en.wikipedia.org/wiki/ROT13)-encoded, so the words aren't in the
  source as plain text. To add one that gets through, run `rot13('word')` in the
  browser console and add the result to `BLOCKED`.

A card-count deck never repeats a word. A timed session starts with 700 different
words, so repeats are rare.

## Versioning

The version and date in the footer are **updated by hand**. Nothing bumps them
automatically. Change both in the same commit as the change they describe, add an entry
to [`CHANGELOG.md`](CHANGELOG.md), and follow [semver](https://semver.org/):

- **Patch** (`1.3.0` → `1.3.1`): bug fixes and wording tweaks.
- **Minor** (`1.3.0` → `1.4.0`): new features or changes to which words appear.
- **Major** (`1.3.0` → `2.0.0`): a redesign, or changes that alter how a session works.

The date is the day of the change, in `YYYY-MM-DD` format.
