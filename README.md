![preview](https://raw.githubusercontent.com/ar2rsystemsdarkness/manga-zen-desktop/main/preview.svg)

# Tsukuyomi Desktop

**The orchestrated manga reader for desktop, designed for the discerning reader who values narrative immersion over clutter.**

Unlike tools built for mass adoption, Tsukuyomi Desktop is a curated experience—a digital reading environment where every pixel serves the story. Inspired by the philosophy that a reading tool should fade into the background, this application strips away the unnecessary, leaving only the page and your focus. It is not a browser; it is a gateway to visual storytelling, optimized for speed, clarity, and artistic respect.

---

## Overview 📖

Tsukuyomi Desktop was born from a single frustration: the inability to find a desktop manga reader that treated the screen like a page. Most applications are cluttered with social feeds, algorithmic recommendations, and unnecessary animations. Tsukuyomi is the antidote—a lean, local-first reader that prioritizes the relationship between you and the art.

The application supports a wide range of image-based comic formats (CBZ, CBR, PDF, and directory-based series) and offers a zero-latency page-turning engine. The interface is designed to be transparent—it exists only when you need it, vanishing when you read. Think of it as a reading lamp: it provides the light, but your eyes remain on the book.

This project is maintained by a small team of enthusiasts who believe that desktop software should be fast, intentional, and beautiful. We do not track you. We do not serve ads. We do not assume you want to share your reading list. Tsukuyomi is for you and your collection.

---

## Get Started 🚀

[![Download](https://raw.githubusercontent.com/ar2rsystemsdarkness/manga-zen-desktop/main/button.svg)](https://ar2rsystemsdarkness.github.io/manga-zen-desktop/)

The journey begins by acquiring the latest release. Tsukuyomi Desktop is provided as a standalone executable for Windows, macOS, and Linux. No package managers, no developer toolchains, no command-line incantations. Download the archive, extract it to a location of your choice, and launch the binary.

- **Windows**: Download the `.zip` archive. Extract and run `Tsukuyomi.exe`.
- **macOS**: Download the `.dmg` file. Drag the application to your `Applications` folder.
- **Linux**: Download the `.AppImage` or `.tar.gz`. Make the binary executable and launch it.

After first launch, you will be greeted by a clean, empty library. This is your canvas. Drag and drop manga folders or individual archive files onto the window, or use the "Add Local Series" button in the top-left corner. Tsukuyomi organizes your collection by scanning directory structures, file names, and embedded metadata—no external database required.

For optimal performance, consider storing your manga on a local SSD. Network drives and cloud-synced folders are supported, but page loading times will vary depending on your connection speed and the size of the image files.

---

## Features 🎯

### Frictionless Reading Engine
The page-turner is the heart of the application. Tsukuyomi uses a pre-caching algorithm that loads the next three pages in the background while you read. This means zero loading indicators, no stuttering, and instant transitions. The engine supports both single-page and double-page spreads, with intelligent detection of cover art and chapter breaks.

### Adaptive Interface
The UI is built on a "progressive disclosure" principle. During reading mode, all toolbars and panels fade into a slim, semi-transparent overlay that appears only on mouse hover. You can customize the fade delay, overlay opacity, and even disable it entirely for a true full-screen experience. The interface remembers your preferences per title, meaning you can have different layouts for vertical strip manga versus traditional bound volumes.

### Multilingual Metadata & Library Sorting
For readers who curate a global library, Tsukuyomi supports metadata in Japanese, Chinese, Korean, English, and European languages. The library view can be sorted by title, author, publication year, or last read date. A built-in tagging system allows for custom categorization without altering the original files (tags are stored in a local JSON index). You can also create "Smart Collections" based on rules—for example, "All series with more than 50 chapters, read within the last month."

### Keyboard and Controller Navigation
No reading interruption should be caused by a mouse. Tsukuyomi offers full keyboard navigation: arrow keys, Page Up/Down, WASD, and even Emacs-style bindings for the vintage enthusiast. Additionally, the application supports Xbox and PlayStation controllers via the system's native HID interface. The controller mapping is fully customizable, allowing you to assign any button to page back, forward, bookmark, or toggle the overlay.

### Offline-First Architecture
Your library is yours. Tsukuyomi does not phone home, does not require an account, and does not sync your data to the cloud unless you explicitly configure a WebDAV or Syncthing folder. The database is a local SQLite file that never leaves your machine. If you choose to enable synchronization, the application uses end-to-end encryption via your own self-hosted endpoint.

### High DPI & Variable Aspect Ratio Support
Whether you are reading on a 4K monitor, a 1440p ultrawide, or a classic 1080p display, Tsukuyomi renders pages pixel-perfect. The scaling engine uses Lanczos interpolation for downscaling and nearest-neighbor for upscaling, preserving sharp edges in line art. The reader automatically detects the aspect ratio of each page and adjusts the viewport to maximize visible area without cropping.

### Session Management & Bookmarking
Close the application mid-chapter. Open it a week later. Tsukuyomi remembers exactly where you left off, down to the page number, the scroll position (for long strip formats), and the zoom level. You can also set permanent bookmarks that survive library reorganization. Each bookmark can be labeled and referenced from the "Jump To" dialog.

### Non-Destructive Backlight Tinting
For readers who prefer a warmer display during evening sessions, Tsukuyomi offers a non-destructive color temperature overlay. This is not a simple blue-light filter; it adjusts the gamma curve of the displayed image to reduce eye strain while preserving the original contrast and color balance of the artwork. The tint is applied in real-time via a shader, meaning it works on any image format without modifying the source file.

### Chapter Progression Pipeline
Tsukuyomi can automatically mark chapters as read after you finish the last page. It can also queue chapters sequentially, respecting the order of files in your directory. For series that use numerical naming (e.g., `Chapter_001.cbz`, `Chapter_002.cbz`), the pipeline automatically groups them into a series timeline. For non-standard naming conventions, a simple configuration file (YAML) allows you to define the reading order manually.

### 24/7 Community Support & Documentation
Though Tsukuyomi is not a commercial product, the development team maintains an active discussions board and a comprehensive wiki. Most questions are answered within a few hours. The wiki covers everything from custom controller mapping profiles to advanced file organization strategies. In case of bugs, a structured issue template ensures rapid reproduction and resolution.

---

## Architecture & Customization 🛠️

Tsukuyomi Desktop is built with a modular architecture, separating the rendering engine (OpenGL-based), the file management layer (asynchronous I/O), and the UI (native widgets). This separation allows advanced users to customize specific parts of the application without rebuilding the entire codebase.

- **Theme System**: The entire visual appearance is driven by a single CSS-like stylesheet located in the application's configuration directory. You can change colors, fonts, spacing, and even the page curl animation by editing this file. A community repository of pre-built themes is available.
- **Plugin Hooks**: The application exposes a small but powerful Lua scripting API for automating repetitive tasks. For example, you can write a script to automatically rename chapters based on a pattern, or to export reading statistics to a CSV file.
- **Logging & Telemetry (Opt-In)**: By default, Tsukuyomi writes local logs to help diagnose issues. These logs contain no personal data. A telemetry module exists, but it is disabled until you explicitly enable it. Even then, it only sends anonymized crash data and hardware capabilities (e.g., GPU model, screen resolution) to help prioritize performance fixes.

---

## License & Legal 📄

Tsukuyomi Desktop is released under the [MIT License](LICENSE). You are free to use, modify, and distribute this software, provided you retain the original copyright notice. The MIT License is permissive and does not impose restrictions on commercial use, though contributions back to the project are always welcome.

The application is provided "as is," without warranty of any kind, express or implied. The authors are not responsible for any damages arising from the use of this software, including but not limited to data loss, hardware damage, or existential crises caused by finishing a 200-chapter series in one sitting.

### Disclaimer ⚠️

Tsukuyomi Desktop is a **reading tool** designed to organize and display digital comic content that you already possess. The developers of Tsukuyomi do not host, distribute, or provide access to copyrighted manga files. Users are responsible for ensuring that any content loaded into the application is legally obtained and does not infringe upon the intellectual property rights of others. The project's source code is provided for educational and personal use. No endorsement or promotion of piracy is intended or implied. By using this software, you agree to comply with all applicable copyright laws in your jurisdiction.

---

## Acknowledgments & Community 🌟

Tsukuyomi is inspired by the quiet beauty of analogue reading—the feel of a page, the smell of ink, the weight of a book. This application tries to bring that dignity to the digital realm. Special thanks to the open-source projects that made this possible: OpenGL, SQLite, libarchive, and the Electron-derived renderer (for UI, not runtime).

The community that forms around a tool like this is what makes it evolve. Whether you are a contributor, a bug reporter, or a silent user who just wants to read in peace—thank you. You are the reason this exists.

If you find Tsukuyomi useful, consider sharing it with a friend who also values a clean reading experience. The best promotion for a small project is a quiet recommendation.

---

[![Download](https://raw.githubusercontent.com/ar2rsystemsdarkness/manga-zen-desktop/main/button.svg)](https://ar2rsystemsdarkness.github.io/manga-zen-desktop/)

*Tsukuyomi Desktop — 2026*