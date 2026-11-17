# 🎙️ Vocab Buddy – Voice Vocabulary Agent

A simple voice agent that helps people learn vocabulary. It speaks a word and its meaning, asks you to use the word in your own sentence (by voice or by typing), checks your answer, and gives you an example.

**Live demo:** https://megsssss.github.io/vocab-buddy/ *(update this link if your repo name is different)*

## Why I built it

Learners remember words better when they use them out loud, not just read definitions. This prototype tests a simple loop: **hear → understand → say → get feedback**, with no sign-up and nothing to install.

## How it works

1. Press **Start session**.
2. The agent speaks a word, its part of speech and its meaning.
3. You answer by tapping **🎤 Speak** or typing a sentence.
4. The agent checks that you used the word in a full sentence and replies with feedback and an example sentence.
5. Tap **Next** to continue. You get a score at the end of the session.

Extra controls: **🔁 Repeat** (hear the meaning again), **💡 Hint**, and **Skip**.

### Feedback logic

- Sentence uses the word and has at least 5 words: counts as correct, and you hear an example.
- Sentence uses the word but is too short: you are asked for a longer sentence.
- Word not used: you get a retry and a hint. After two tries, the agent gives an example and lets you move on.

The word check matches the start of the word (so "resilience" or "resilient" both count). It checks that the word was used, not that it was used correctly.

## Tech

- Single file: plain HTML, CSS and JavaScript, with no frameworks, build step or external libraries
- **Web Speech API** for voice: `SpeechSynthesis` for the agent’s voice and `SpeechRecognition` for your answers
- Light and dark mode follow your device setting
- Works on mobile and desktop

## Run it locally

1. Download `index.html`.
2. Open it in Chrome or Edge.

## Browser support

| Feature | Chrome / Edge | Safari / Firefox |
|---|---|---|
| Agent speaks | Yes | Mostly yes |
| Voice input | Yes | Limited or not supported (falls back to typing) |

Voice input needs microphone permission. If it is blocked or unsupported, you can always type your sentence.

## Customize the words

The word list is the `WORDS` array near the top of the script in `index.html`. Each entry has:

```js
{ w: "candid", p: "adjective", d: "honest and direct...", e: "Example sentence.", h: "Hint text." }
```

Add, remove or edit entries to create your own set.

## Limitations

- Only 8 built-in words.
- Sentence checking is rule-based, so it can’t judge meaning or grammar.
- Progress isn’t saved between sessions.

## Ideas for next steps

- Use an LLM to judge whether the word is used correctly and give personalized feedback
- Spaced repetition, so missed words come back later
- Difficulty levels and topic packs, such as interview or workplace vocabulary
- Save progress and streaks per learner
- Track which words learners struggle with, to improve the word list

## Author

Built by **Megha Yewale** as a quick prototype. [LinkedIn](https://www.linkedin.com/in/megha-yewale-302856272/) • [GitHub](https://github.com/megsssss)
