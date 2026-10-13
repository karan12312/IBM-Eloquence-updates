# IBM Eloquence for Android — Official Release & Updates Repository

Official distribution repository and OTA update manifest host for **IBM Eloquence TTS for Android**.

---

## 🚀 Latest Release: v1.0.378 (Build 379)

* **Release Date:** October 13, 2026
* **Package Name:** `com.karan.eloquence`
* **Direct Download:** [IBM Eloquence_1.0.378.apk](https://github.com/karan12312/IBM-Eloquence-updates/raw/main/IBM%20Eloquence_1.0.378.apk)
* **File Size:** 52.06 MB (54,585,260 bytes)
* **SHA-256 Checksum:** `5c3677d346b1e65fcfcde3279f0af6170122c84492799bdd9bc3971b5a42cb75`

---

## 📋 What's New in v1.0.378

### 1. Fixed Abbreviations Expansion & Dotted Titles
* **In-Band Annotation Inversion Resolved:** Restored proper in-band dictionary annotation (`da1` ON, `da0` OFF) so toggling abbreviations on immediately enables synthesizer expansion ("Dr." -> "Doctor", "Mr." -> "Mister", "St." -> "Street") during TalkBack reading and speech delivery tests.
* **Intact Sentence Boundary & Pause Processing:** Fixed dotted abbreviation handling so sentence-end pause markers are not inserted inside titles (e.g. "Dr. Smith"), keeping tokens unified for the dictionary lookup engine.

### 2. Dictionary Lookup Precedence
* **Longest Match Priority:** Overlapping dictionary entries at identical text indices now sort longest-first, ensuring compound terms (e.g. "New York") are not shadowed by shorter prefixes ("New").
* **Phonetic Replacement Cleanup:** Sanitized dictionary substitution entries to eliminate rogue pronunciation characters from appearing as raw text in spoken output.

### 3. Punctuation & Special Symbols Standardization
* **Symbol vs. Emoji Classification:** Copyright (`©`), Registered (`®`), and Trademark (`™`) are recognized strictly as punctuation rather than emoji, respecting punctuation verbosity levels (silent under None, verbalized from Some upward).
* **Stripped Emoji Selectors:** Removed extraneous emoji presentation selectors trailing punctuation symbols.

### 4. Natural Emoji Readings
* **Plain Emoji Descriptions:** Stripped redundant "emoji" prefixes from Unicode character names.
* **Skin Tone & Flag Handling:** Refined descriptions for skin-tone modifiers and fallback flag sequences.
* **Optimized Lookup:** Eliminated redundant emoji table scans for standard numeric and keypad characters.

### 5. Hardened OTA Updater Pipeline
* **Safe, Verified Downloads:** Self-cleaning temporary files, streaming SHA-256 integrity checks, and single-flight download concurrency.
* **Resilient FileProvider Mapping:** Fully resolved root collisions for seamless in-app package installations across all Android versions.

---

## 📲 How to Install / Update

1. Download [`IBM Eloquence_1.0.378.apk`](https://github.com/karan12312/IBM-Eloquence-updates/raw/main/IBM%20Eloquence_1.0.378.apk).
2. Open the APK on your Android device and confirm installation.
3. If updating from within the app, navigate to **Settings > Check for Updates** to trigger the built-in OTA updater.

---

## 🔒 Verification & Integrity

Verify the integrity of your downloaded APK using SHA-256:

```bash
# Linux / macOS
sha256sum "IBM Eloquence_1.0.378.apk"

# Windows PowerShell
Get-FileHash -Path "IBM Eloquence_1.0.378.apk" -Algorithm SHA256
```

Expected hash:
`5c3677d346b1e65fcfcde3279f0af6170122c84492799bdd9bc3971b5a42cb75`
