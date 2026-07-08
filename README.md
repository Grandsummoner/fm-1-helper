# M-Wave FM-1 SysEx Patch Curator Pro

A web-based utility designed for the **M-VAVE FM-1** that enables users to curate, manage, and compile custom DX7-compatible SysEx banks[cite: 1]. This tool streamlines the process of ingesting voice data and preparing stable, bank-ready files for hardware transmission[cite: 1].

---

![Module Graphic](./res/Subtraktor.png)


## Features

* **Drag-and-Drop Ingestion**: Easily load standard 4104-byte `.syx` or `.bin` files via drag-and-drop or folder selection[cite: 1].
* **Intelligent Bank Management**: Organize patches into four distinct banks (A–D) with 32 slots each[cite: 1].
* **Data Integrity**: Auto-fills empty destination slots with "INIT VOICE" data to prevent performance glitches or truncation errors[cite: 1].
* **Web MIDI Integration**: Directly transmit curated banks to your FM-1 hardware via the browser[cite: 1].
* **Sort & Compact**: Built-in sorting and packing utilities to maintain a clean workspace[cite: 1].

## How to Use

* **Request MIDI Access**: Click the **Request Web MIDI Access** button in the top right to link your FM-1 hardware[cite: 1].
* **Import Sources**: Drop your existing SysEx library files into the **Source Importer** panel[cite: 1].
* **Curate**:
    * Drag patches from the **Global Preset Pool** into your target slots in the **Destination Banks**[cite: 1].
    * Use the **🎲 Roll** button to randomize patches into a bank[cite: 1].
    * Use the **🔄 Pack** button to remove gaps and align patches[cite: 1].
* **Export/Send**:
    * Click **💾 Export Active Bank .SYX** to save a file to your disk[cite: 1].
    * Click **⚡ Send Active Bank to FM-1** to transmit the data directly via MIDI[cite: 1].

## Technical Specifications

| Feature | Specification |
| :--- | :--- |
| **Compatibility** | DX7 SysEx architecture (4104 bytes per bank)[cite: 1] |
| **Browser Support** | Optimized for Chromium-based browsers (Chrome, Edge, Opera)[cite: 1] |

## Troubleshooting

* **"No MIDI Hardware Found"**: Ensure your M-VAVE FM-1 is connected via USB and powered on before launching the application[cite: 1].
* **MIDI Port In Use**: If the MIDI send fails, ensure no other DAW or SysEx librarian software is occupying the MIDI port[cite: 1].
* **Browser Permissions**: Ensure your browser is allowed to access MIDI devices via the site settings[cite: 1].

---

> **Note:** This utility is provided for educational and creative use. Always back up your existing hardware data before performing a bulk SysEx dump[cite: 1].
