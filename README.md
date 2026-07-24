# 🚀 [Tips Hindawi](https://www.tipshindawi.com/) Challenge (June–July) 2026

> 🏆 This repository is my official submission for the [ **Tips Hindawi** ](https://www.tipshindawi.com/) **Challenge (June–July) 2026**.

## 👤 Participant

| Field            | Value                                |
| ---------------- | ------------------------------------ |
| Full Name        |                                       |
| Project Name     | YouTube Flashcards                   |
| GitHub Username  |                                       |
| Challenge Batch  | June–July 2026                       |
| Training Program | Large Language Models (LLMs) Program |
| Organization     | [**Edrak for Ai**](https://edrak4ai.com/en) |

---

# 📖 Project Overview

**YouTube Flashcards** is a mobile app that turns any YouTube video with subtitles into a ready-to-study set of language-learning flashcards.

The user pastes a YouTube link and picks a target language (the one they're learning) and a native language (the one they understand). The backend fetches the video's transcript, sends it to an LLM to extract the most useful vocabulary, generates example sentences and audio pronunciation for each word, and returns a complete flashcard deck to the app — where it's saved locally, can be reviewed with a flip-card UI, read aloud, renamed, or merged with other decks.

The project has two parts:

* **Flutter mobile app** (`lib/`) — the UI, local storage, and text-to-speech playback.
* **Python/Flask backend** (`project.ipynb`) — runs on Kaggle (GPU notebook), exposed publicly via ngrok, and handles transcript extraction, LLM-based flashcard generation, and audio synthesis.

---

# ✨ Features

* 🔗 **Generate flashcards from any YouTube link** with available subtitles.
* 🌍 **12 supported languages** (English, Arabic, Spanish, French, German, Turkish, Italian, Japanese, Korean, Russian, Chinese, Portuguese) — pick any target/native pair.
* 🤖 **LLM-powered extraction** using Qwen2.5-VL-72B-Instruct (via Hugging Face Inference API) to pick the most important vocabulary and generate example sentences with translations.
* 🔊 **Dual text-to-speech**: high-quality server-generated audio (gTTS) with automatic fallback to on-device TTS (`flutter_tts`) when offline.
* 🃏 **Flip-card review screen** with smooth 3D flip animation, swipe navigation, and progress tracking.
* 💾 **Fully offline-capable local storage** — decks are saved as JSON files on the device, no account or internet needed to review saved decks.
* 🔀 **Merge multiple decks** that share the same language pair into one, automatically removing duplicate terms.
* ✏️ **Rename and delete decks**, with a bulk multi-select mode for merging.
* ⚙️ **In-app server settings** — paste the ngrok server URL and test the connection before generating.
* 📋 **One-tap paste** for both the YouTube link and the server URL.
* 🇸🇦 **Fully Arabic UI**.

---

# 🛠️ Technologies Used

**Mobile app (Flutter):**
* Flutter & Dart (Material 3)
* `http` — communication with the backend API
* `path_provider` & `shared_preferences` — local deck storage and settings
* `flutter_tts` — on-device text-to-speech fallback
* `audioplayers` — playback of server-generated audio

**Backend (Python, Kaggle notebook):**
* Flask + Flask-CORS — REST API
* `pyngrok` — public tunnel to the Kaggle notebook
* `youtube-transcript-api` — fetching video transcripts
* `huggingface_hub` (`InferenceClient`) — LLM inference (Qwen2.5-VL-72B-Instruct)
* `langchain` — structured output parsing of the LLM's flashcard response
* `gTTS` — text-to-speech audio generation

---

# ⚙️ Installation

### Backend (Kaggle notebook)

1. Open `project.ipynb` in a Kaggle notebook with **GPU** and **Internet access** enabled.
2. Add your secrets in **Add-ons → Secrets**:
   * `HAGING FACE` — your Hugging Face API token.
   * `NGROK` — your ngrok auth token.
3. Run all cells. The last cell prints a public `ngrok` URL — copy it.

### Mobile app (Flutter)

1. Make sure the Flutter SDK is installed.
2. From the project root, install dependencies:
   ```bash
   flutter pub get
   ```
3. Run the app on a connected device or emulator:
   ```bash
   flutter run
   ```

---

# 🚀 Usage

1. Launch the app and tap the **server settings** icon (🖥️ top bar), paste the ngrok URL from the notebook, and test the connection.
2. Tap **"مجموعة جديدة" (New deck)**, paste a YouTube video link, choose the target and native languages, and tap **"توليد البطاقات" (Generate flashcards)**.
3. Give the new deck a name and start reviewing — tap a card to flip it, swipe or use the arrows to move between cards, and tap the speaker icon to hear the pronunciation.
4. From the home screen, you can rename or delete any deck, or select multiple decks with the same language pair to merge them.

---

# 📸 Demo

<img width="540" height="1158" alt="WhatsApp Image 2026-07-24 at 4 01 07 PM" src="https://github.com/user-attachments/assets/eea2fdf4-0952-49c7-8783-6a5fb0b624a9" />

<img width="540" height="1143" alt="WhatsApp Image 2026-07-24 at 3 57 23 PM" src="https://github.com/user-attachments/assets/559eaf0f-e4ab-4fba-9a6b-b27cd3f5eff8" />


---

# 📈 Results

*Add outcomes here — e.g. number of decks/videos tested, generation speed, accuracy of extracted vocabulary, or feedback from testers.*

---

# 🔮 Future Improvements

* Spaced-repetition scheduling (e.g. SM-2) for smarter review order instead of a plain sequential deck.
* Support for videos without official subtitles via automatic speech recognition.
* Deploy the backend on a persistent server instead of a Kaggle notebook + ngrok tunnel.
* Export/import decks and share them between users.
* Dark mode and additional UI languages.

---

# 📚 About the Challenge

This project was developed as part of the [**Tips Hindawi**](https://www.tipshindawi.com/) **Challenge (June–July) 2026**.

[Tips Hindawi](https://www.tipshindawi.com/) is the internships department of [**Edrak for Ai**](https://edrak4ai.com/en), and the challenge encourages participants to build real-world projects, apply practical skills, and showcase their work through GitHub.

For more information about the challenge, training programs, and upcoming batches, visit the official [Tips Hindawi](https://www.tipshindawi.com/) website.

---

# 📄 License

This project is shared for educational and portfolio purposes.
