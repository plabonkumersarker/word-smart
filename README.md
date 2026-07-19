# Word Smart Vocabulary Explorer

A fast, searchable vocabulary reference covering every word from **Word Smart Book I & II** — built for BCS and Bangladesh Bank exam prep. Each entry includes the English meaning, Bangla translation, synonyms, and example sentences.

**Live site:** [plabonkumersarker.github.io/word-smart](https://plabonkumersarker.github.io/word-smart)

---

## Features

- **1600+ words** from Word Smart I & II, fully searchable
- **Search by word, index number, or range** (e.g. `1-3`) to jump straight to a section
- **Expandable cards** — tap a word to smoothly reveal its meaning, Bangla translation, synonyms, and example sentences
- **Text-to-speech pronunciation** for every word
- **Dark / light theme toggle**, remembered across visits
- **Lazy-loaded rendering** — only builds the cards currently on screen instead of all 1600+ at once, so it stays smooth even on mobile
- Zero frameworks, zero build step — just open it in a browser

## Tech Stack

Plain HTML, CSS, and JavaScript. No dependencies, no bundler, no backend. The Web Speech API handles pronunciation, and an `IntersectionObserver` drives infinite-scroll style batched rendering.

## Project Structure

```
word-smart/
├── index.html   # UI, styling, and app logic
└── potato.js    # Vocabulary data (words, meanings, sentences, synonyms)
```

Splitting the data into `potato.js` keeps the word list separate from the app logic and lets the browser cache it across visits.

## Running Locally

Clone the repo and open `index.html` in a browser — no server or build step required, as long as `index.html` and `potato.js` are in the same folder.

```bash
git clone https://github.com/plabonkumersarker/word-smart.git
cd word-smart
open index.html   # or just double-click it
```

## Adding Words

Each entry in `potato.js` follows this shape:

```js
{
  "id": 1,
  "word": "abdicate",
  "meaning": "To step down from a position of power or responsibility",
  "bangla_meanings": ["ত্যাগ করা", "পরিত্যাগ করা"],
  "sentences": [
    "The king decided to abdicate and pass his throne to his eldest son.",
    "After years in office, she finally had to abdicate due to health reasons.",
    "He was forced to abdicate after being found guilty of corruption by the court."
  ],
  "synonyms": ["renounce"]
}
```

Add a new object to the `vocabList` array with the next sequential `id`, and it'll appear automatically — no other code changes needed.

## Credits

Built by [Plabon Kumer Sarker](https://plabonkumersarker.github.io/profile).

## License

MIT
