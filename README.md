<div align="center">
  <a href="https://readest.com?utm_source=github&utm_medium=referral&utm_campaign=readme" target="_blank">
    <img src="https://github.com/readest/readest/blob/main/apps/readest-app/src-tauri/icons/icon.png?raw=true" alt="Readest Logo" width="20%" />
  </a>
  <h1>GemReadest</h1>
  <br>

GemReadest is a fork of [Readest][link-website] which is an open-source ebook reader designed for immersive and deep reading experiences. Built as a modern rewrite of [Foliate](https://github.com/johnfactotum/foliate), it leverages [Next.js 16](https://github.com/vercel/next.js) and [Tauri v2](https://github.com/tauri-apps/tauri) to deliver a smooth, cross-platform experience across macOS, Windows, Linux, Android, iOS, and the Web.

</div>

<p align="center">
  <a href="#features">Features</a> •
  <a href="#planned-features">Planned Features</a> •
  <a href="#screenshots">Screenshots</a> •
  <a href="#downloads">Downloads</a> •
  <a href="#getting-started">Getting Started</a> •
  <a href="#troubleshooting">Troubleshooting</a> •
  <a href="#support">Support</a> •
  <a href="#license">License</a>
</p>

<div align="center">
  <a href="https://readest.com" target="_blank">
    <img src="./data/screenshots/landing_all_platforms.png" alt="Readest Banner" width="100%" />
  </a>
</div>

## Features

<div align="left">✅ Implemented</div>

| **Feature**                                | **Description**                                                                                                        | **Status** |
| ------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------- | ---------- |
| **Multi-Format Support**                   | Support EPUB, MOBI, KF8 (AZW3), FB2, CBZ, TXT, PDF                                                                     | ✅         |
| **Scroll/Page View Modes**                 | Switch between scrolling or paginated reading modes.                                                                   | ✅         |
| **Full-Text Search**                       | Search across the entire book to find relevant sections.                                                               | ✅         |
| **Annotations and Highlighting**           | Add highlights, bookmarks, and notes to enhance your reading experience and use instant mode for quicker interactions. | ✅         |
| **Dictionary/Wikipedia Lookup**            | Instantly look up words and terms when reading.                                                                        | ✅         |
| **[Parallel Read][link-parallel-read]**    | Read two books or documents simultaneously in a split-screen view.                                                     | ✅         |
| **Customize Font and Layout**              | Adjust font, layout, theme mode, and theme colors for a personalized experience.                                       | ✅         |
| **Code Syntax Highlighting**               | Read software manuals with rich coloring of code examples.                                                             | ✅         |
| **File Association and Open With**         | Quickly open files in Readest in your file browser with one-click.                                                     | ✅         |
| **Library Management**                     | Organize, sort, and manage your entire ebook library.                                                                  | ✅         |
| **OPDS/Calibre Integration**               | Integrate OPDS/Calibre to access online libraries and catalogs.                                                        | ✅         |
| **Translate with DeepL and Yandex**        | From a single sentence to the entire book—translate instantly.                                                         | ✅         |
| **Text-to-Speech (TTS) Support**           | Enjoy smooth, multilingual narration—even within a single book.                                                        | ✅         |
| **Sync across Platforms**                  | Synchronize book files, reading progress, notes, and bookmarks across all supported platforms.                         | ✅         |
| [**Sync with Koreader**][link-kosync-wiki] | Synchronize reading progress, notes, and bookmarks with [Koreader][link-koreader] devices.                             | ✅         |
| **Accessibility**                          | Provides full keyboard navigation and supports for screen readers such as VoiceOver, TalkBack, NVDA, and Orca.         | ✅         |
| **Visual & Focus Aids**                    | Reading ruler, paragraph-by-paragraph reading mode, and speed reading features.                                        | ✅         |

## Planned Features

<div align="left">🛠 Building</div>
<div align="left">🔄 Planned</div>

| **Feature**                     | **Description**                                                            | **Priority** |
| ------------------------------- | -------------------------------------------------------------------------- | ------------ |
| **AI-Powered Summarization**    | Generate summaries of books or chapters using AI for quick insights.       | 🛠           |
| **Advanced Reading Stats**      | Track reading time, pages read, and more for detailed insights.            | 🛠           |
| **Audiobook Support**           | Extend functionality to play and manage audiobooks.                        | 🔄           |
| **Handwriting Annotations**     | Add support for handwriting annotations using a pen on compatible devices. | 🔄           |
| **In-Library Full-Text Search** | Search across your entire ebook library to find topics and quotes.         | 🔄           |

## Screenshots

![Annotations](./data/screenshots/annotations.png)

![TTS](./data/screenshots/tts_speak_aloud.png)

![DeepL](./data/screenshots/deepl.png)

![Footnote](./data/screenshots/footnote_popover.png)

![Wikipedia](./data/screenshots/wikipedia_vertical.png)

![Theming Dark Mode](./data/screenshots/theming_dark_mode.png)

---

## Requirements

- **Node.js** and **pnpm** for Next.js development
- **Rust** and **Cargo** for Tauri development

For the best experience to build Readest for yourself, use a recent version of Node.js and Rust. Refer to the [Tauri documentation](https://v2.tauri.app/start/prerequisites/) for details on setting up the development environment prerequisites on different platforms.

```bash
nvm install v24
nvm use v24
npm install -g pnpm
rustup update
```

## Getting Started

To get started with Readest, follow these steps to clone and build the project.

### 1. Clone the Repository

```bash
git clone https://github.com/readest.gem/readest.git
cd readest
```

### 2. Install Dependencies

```bash
# might need to rerun this when code is updated
git submodule update --init --recursive
pnpm install
# copy vendors dist libs to public directory
pnpm --filter @readest/readest-app setup-vendors
```

### 3. Verify Dependencies Installation

To confirm that all dependencies are correctly installed, run the following command:

```bash
pnpm tauri info
```

This command will display information about the installed Tauri dependencies and configuration on your platform. Note that the output may vary depending on the operating system and environment setup. Please review the output specific to your platform for any potential issues.

For Windows targets, “Build Tools for Visual Studio 2022” (or a higher edition of Visual Studio) and the “Desktop development with C++” workflow must be installed. For Windows ARM64 targets, the “VS 2022 C++ ARM64 build tools” and "C++ Clang Compiler for Windows" components must be installed. And make sure `clang` can be found in the path by adding `C:\Program Files (x86)\Microsoft Visual Studio\2022\BuildTools\VC\Tools\Llvm\x64\bin` for example in the environment variable `Path`.

### 4. Build for Development

```bash
# Start development for the Tauri app
pnpm tauri dev
# or start development for the Web app
pnpm dev-web
# preview with OpenNext build for the Web app
pnpm preview
```

For Android:

```bash
# Initialize the Android environment (run once)
rm apps/readest-app/src-tauri/gen/android
pnpm tauri android init
pnpm tauri icon ../../data/icons/readest-book.png
git checkout apps/readest-app/src-tauri/gen/android

pnpm tauri android dev
# or if you want to dev on a real device
pnpm tauri android dev --host
```

For iOS:

```bash
# Set up the iOS environment (run once)
pnpm tauri ios init
pnpm tauri icon ../../data/icons/readest-book.png

pnpm tauri ios dev
# or if you want to dev on a real device
pnpm tauri ios dev --host
```

### 5. Build for Production

```bash
pnpm tauri build
pnpm tauri android build
pnpm tauri ios build
```

Please refer to our release script if you experience any issues:
https://github.com/readest/readest/blob/main/.github/workflows/release.yml

### 6. Setup dev environment with Nix

If you have Nix installed, you can leverage flake to enter a development shell
with all the necessary dependencies:

```bash
nix develop ./ops  # enter a dev shell for the web app
nix develop ./ops#ios # enter a dev shell for the ios app
nix develop ./ops#android # enter a dev shell for the android app
```
[link-deepwiki]: https://deepwiki.com/readest/readest
[link-locales]: https://github.com/readest/readest/tree/main/apps/readest-app/public/locales
[link-kosync-wiki]: https://github.com/readest/readest/wiki/Sync-with-Koreader-devices
[link-reddit]: https://reddit.com/r/readest/
