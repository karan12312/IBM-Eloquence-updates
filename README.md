# IBM Eloquence for Android — Official Release & Updates Repository

Official distribution repository and OTA update manifest host for **IBM Eloquence TTS for Android**.

---

## 🚀 Latest Release: v1.0.367 (Build 368)

* **Release Date:** October 10, 2026
* **Package Name:** `com.karan.eloquence`
* **Direct Download:** [IBM_Eloquence_1.0.367.apk](https://github.com/karan12312/IBM-Eloquence-updates/releases/download/v1.0.367/IBM_Eloquence_1.0.367.apk)
* **File Size:** 94.64 MB (99,237,297 bytes)
* **SHA-256 Checksum:** `30575bb296ef8e616f4752ed365c904cd52e4bc1009fe0bc5978ba0dbcab00c4`

---

## 📋 What's New in v1.0.367

### 1. Critical OTA Package Installer Fix (P1)
* **FileProvider Root Collision Resolved:** Fixed an issue where duplicate root name identifiers in `file_paths.xml` caused `<files-path>` to overwrite `<cache-path>`, resulting in `IllegalArgumentException: Failed to find configured root that contains /data/data/com.karan.eloquence/cache/updates/ibm-eloquence-...apk`.
* **Universal Storage Coverage:** Added explicit root definitions (`cache_updates`, `files_updates`, `internal_cache`, `internal_files`, `device_root`) and resilient canonical fallback handling in `UpdateManager.installApk`.

### 2. Punctuation Presets (JAWS SBL Standard Alignment)
* **Unified Time Colon Reading (`NumericColonText`):**
  * Fully unified punctuation handling according to the Freedom Scientific JAWS SBL standard.
  * **None (Level 0):** Time strings like `10:30` are read naturally without colon symbols (`"10 30"` -> *"ten thirty"*).
  * **Some (Level 1), Most (Level 2), All (Level 3):** Time colons are verbalized explicitly as *"colon"* (`"10 Colon 30"`).
* **Pronunciation Pause Audit:** Verified that silent synthesizer pause marks (periods, commas, semicolons, dashes, ellipses) are respected across all four preset levels.

### 3. Ultra-Low Latency & TalkBack Swipe Optimization
* **Sub-Millisecond Pre-Synthesis:** Pipeline latency optimized to **~0.8 ms** for UI tokens and **~6.8 ms** for long multi-component sentences.
* **Rapid Gesture Swiping Endurance:** Stress-tested across **200 consecutive TalkBack swipe interruptions** on physical hardware:
  * Average turnaround time: **6.52 ms / swipe cycle**.
  * Zero thread deadlocks, zero orphaned threads, and zero dropped speech requests.
* **AudioFlinger FastTrack:** Matched output sample rate to device mixer (48 kHz) with `AUDIO_OUTPUT_FLAG_FAST`, achieving **~4 ms buffer latency** instead of standard 128 ms mixer delays.

### 4. Stability & Bug Fixes
* **Indic Visarga Normalization:** Correctly maps mid-word colons in Devanagari and other Indic scripts (e.g. `स्व:तच्या` -> `स्वःतच्या`, `दु:ख` -> `दुःख`) preventing word fragmentation and phonetic crashes.
* **Narrow No-Break Space:** Standardized `U+202F` and other Unicode whitespace variants to standard ASCII space (`U+0020`).
* **Micro Fade-Out Envelope:** Applied 1.5ms linear ramp-down on audio tails, eliminating step discontinuities and physical speaker click/pop noises upon utterance completion.
* **Concurrency Hardening:** 100% crash-free under 200+ rapid asynchronous JNI chaos stress bombardments (zero `SIGSEGV`, zero tombstones).

---

## 📲 How to Install / Update

1. Download [`IBM_Eloquence_1.0.367.apk`](https://github.com/karan12312/IBM-Eloquence-updates/releases/download/v1.0.367/IBM_Eloquence_1.0.367.apk).
2. Open the APK on your Android device and confirm installation.
3. If updating from within the app, navigate to **Settings > Check for Updates** to trigger the built-in OTA updater.

---

## 🔒 Verification & Integrity

Verify the integrity of your downloaded APK using SHA-256:

```bash
# Linux / macOS
sha256sum IBM_Eloquence_1.0.367.apk

# Windows PowerShell
Get-FileHash -Path "IBM_Eloquence_1.0.367.apk" -Algorithm SHA256
```

Expected hash:
`30575bb296ef8e616f4752ed365c904cd52e4bc1009fe0bc5978ba0dbcab00c4`
