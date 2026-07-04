# Subtraktor: Elektron Tonverk .eldrum Kit Creator

Subtraktor is a lightweight, browser-based, offline utility designed specifically for the **Elektron Tonverk** hardware platform. It streamlines the creation, curation, and optimization of custom drum kits mapped to the Tonverk’s native **Subtrack** machine type.

By handling file resampling, metadata mapping, and visual trimmer cropping completely client-side, Subtraktor ensures your custom sounds are fully optimized and ready to run on the Tonverk hardware.

---

![Module Graphic](./res/Subtraktor.png)

## 🚀 Live Application
Use the hosted web utility directly in your browser:  
👉 **https://Grandsummoner.github.io/subtraktor/Subtraktor.html**

---

## 📂 How It Works
The utility serves three primary functions:

1.  **Native Sample Transcoding:** The Tonverk hardware engine plays uncompressed linear PCM audio natively at 48,000 Hz. Subtraktor takes user audio uploads in almost any format (including WAV, MP3, FLAC, AIFF, M4A, OGG, AAC, or OPUS) and automatically decodes, downmixes, and resamples them in-browser to a standardized **16-bit, 48 kHz, Stereo LPCM WAV** container. This ensures zero resampling latency, avoids pitch-shifting bugs, and guarantees click-free playback on the hardware.

2.  **Visual Parameter Mapping (`.eldrum`):** The app maps the files to 8 active trigger slots corresponding to the standardized Subtrack MIDI notes (notes 60 through 72: Kick, Snare, Tom, Clap, Cowbell, Closed Hat, Open Hat, and Cymbal). It allows you to customize the velocity, playback strategy (Forward, Reverse, or Ping-Pong), and category mappings. It compiles these assignments into a single `.eldrum` TOML-formatted metadata file.

3.  **Non-Destructive Trimming & Optimization:** The integrated visual editor provides interactive pointer-locked handles on each waveform, letting you set custom crop points (start and end trim boundaries). During export, only the trimmed area is written to the final output file, and an optional Gain Normalisation scans the peaks to scale the audio to a safe -1.0 dBFS baseline, maximizing headroom and signal-to-noise ratio.

Ultimately, Subtraktor outputs a single `.zip` package containing your customized, optimized `.wav` files alongside the corresponding `.eldrum` layout file.

---

## 💾 Elektron Tonverk SD Card Setup
For the Tonverk engine to recognize and load your custom drum set, the files must be laid out on your SD card in a specific directory structure:

1.  **Extract the exported `.zip`** package created by the app. 
2.  You will get a folder containing your `.wav` sample files and a single `.eldrum` file (e.g., `Pizzac.eldrum` and its associated samples).
3.  Connect your Tonverk SD card to your computer and transfer the entire folder to the user directory:
    ```text
    SD Card / User / Drum Sets / [YourKitName] /
    ```
4.  **Important Folder Rules:**
    *   The folder on the SD card must have the **exact same name** as your `.eldrum` file (e.g., if the file is `Pizza.eldrum`, the folder must be named `Pizza`).
    *   The `.eldrum` file and all the converted `.wav` samples must sit flatly together inside this folder. Do not place the samples inside subdirectories.
    *   On the Tonverk, load a **Subtrack machine type** and select your custom drum kit from the machine menu.

---

## ✨ Key Features

-   **Format Transcoding:** Drag and drop audio in almost any format. The browser automatically transcodes them into standard 16-bit, 48 kHz, Stereo LPCM WAV files for native, low-latency playback.

-   **Precision Trimmer:** Set exact start and end trim boundaries on an interactive visual waveform canvas. Only the trimmed portion of the file is rendered during export, keeping file sizes to a minimum.

-   **Safe Gain Normalisation:** Optionally scales the peak amplitude of all exported WAV files to exactly -1.0 dBFS for optimized headroom and maximum signal-to-noise ratio.

-   **Existing File Viewer:** Drag and drop or upload an existing `.eldrum` file to inspect its note layout, category structure, and velocity mappings.

-   **Local Persistence & Autosafe:** The workspace state, selected themes, and imported audio files are preserved locally inside your browser's IndexedDB database. You can close or reload the browser tab without losing your loaded assets, and you are free to reorganize or delete the original files on your computer's hard drive.

---

## 📊 Technical Specifications

*   **Target Output Resolution:** 16-bit / 48,000 Hz / Stereo Interleaved LPCM WAV.

*   **MIDI Note Mapping Layout:**
    *   **Slot 01 (Kick):** MIDI Note 60 (C3)
    *   **Slot 02 (Snare):** MIDI Note 62 (D3)
    *   **Slot 03 (Tom/Perc):** MIDI Note 64 (E3)
    *   **Slot 04 (Clap/Perc):** MIDI Note 65 (F3)
    *   **Slot 05 (Cowbell/Perc):** MIDI Note 67 (G3)
    *   **Slot 06 (Closed Hat):** MIDI Note 69 (A3)
    *   **Slot 07 (Open Hat):** MIDI Note 71 (B3)
    *   **Slot 08 (Cymbal/Perc):** MIDI Note 72 (C4)

*   **Supported Playback Strategies:** Forward (FWD), Backward/Reverse (REV), and Ping-Pong (PPG).

---

## 🔒 Privacy & Offline Use
Subtraktor does not collect, track, or upload your audio files or personal data to any external servers. All decoding, rendering, resampling, and ZIP packaging processes take place entirely inside your local browser sandbox.
