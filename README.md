# 📇 Puttogether

**A privacy-first card number extraction tool that runs entirely in your browser.**

Extract payment card numbers from files, photos, and text — without ever uploading your data to a server.

**Live site:** https://puttogether.netlify.app

---

## 📸 Screenshots

<details>
<summary>Click to view screenshots</summary>

### Main Interface
![Main Interface](screenshots/main-interface.png)
*The clean, mobile-first landing page with all input source options*

### Source Selection
![Source Selection](screenshots/source-selection.png)
*Six different ways to input your files and text*

### Processing Status
![Processing Status](screenshots/processing-status.png)
*Real-time feedback during OCR and file processing*

### Results Display
![Results Display](screenshots/results-display.png)
*Extracted card numbers with type detection and copy functionality*

### Mobile View
![Mobile View](screenshots/mobile-view.png)
*Fully responsive design optimized for mobile devices*

*Note: Screenshots to be added. See [screenshots/README.md](screenshots/README.md) for details on how to contribute screenshots.*

</details>

---

## 🎯 Purpose

Puttogether helps you extract payment card numbers from various sources quickly and securely. Whether you're organizing financial documents, processing receipts, or recovering card information from old files, Puttogether makes it easy — all while keeping your data completely private.

**Key benefits:**
- **Mobile-first design** — Works seamlessly on phones and tablets
- **100% client-side processing** — Your data never leaves your device
- **No installation required** — Works directly in your browser
- **Multiple input methods** — Upload files, take photos, paste text, and more

---

## 🔍 How Card Extraction Works

Puttogether uses a sophisticated three-step process to find and validate card numbers:

### 1. Pattern Recognition

The app searches for card numbers using brand-specific patterns:

- **Visa**: Starts with 4, 16 digits
- **Mastercard**: Starts with 51-55 or 2221-2720, 16 digits
- **American Express**: Starts with 34 or 37, 15 digits
- **Discover**: Starts with 6011 or 65, 16 digits
- **Diners Club**: Starts with 300-305 or 36/38, 14 digits
- **JCB**: Starts with 2131, 1800, or 35, 15-16 digits

The patterns recognize numbers with various formatting:
- Plain digits: `4532123456789012`
- Space-separated: `4532 1234 5678 9012`
- Hyphen-separated: `4532-1234-5678-9012`

### 2. Luhn Algorithm Validation

Every potential card number is validated using the [Luhn checksum algorithm](https://en.wikipedia.org/wiki/Luhn_algorithm), the industry-standard validation method used by all payment card providers. This eliminates false positives from random number sequences.

### 3. Deduplication & Formatting

Duplicate numbers are automatically removed, and results are formatted for easy reading:
- Standard cards: `XXXX XXXX XXXX XXXX`
- Amex: `XXXX XXXXXX XXXXX`
- Diners: `XXXX XXXXXX XXXX`

---

## 🔒 Privacy Safeguards

Your privacy and security are our top priorities. Here's how Puttogether protects your data:

### ✅ Client-Side Only Processing

- **No server uploads**: All file processing happens entirely in your browser
- **No data transmission**: Your files and card numbers never leave your device
- **No tracking**: No analytics, cookies, or data collection of any kind

### ✅ No Data Storage

- **Memory-only**: Extracted card numbers exist only in browser memory while you're using the app
- **Instant clearing**: Results disappear when you click "Clear" or close your browser
- **No persistence**: No localStorage, IndexedDB, or any form of data storage

### ✅ Open Source Libraries

The app uses well-established, open-source libraries for file processing:
- **PDF.js** (Mozilla) — Extracts text from PDF files
- **Tesseract.js** — Performs OCR on images

Both libraries are loaded from trusted CDNs and contain no tracking code.

### ✅ What This Means For You

When you use Puttogether:
- Your files are never uploaded to a server
- No one (including us) can see your data
- No records are kept of your activity
- No accounts or login required
- Works completely offline after the initial page load

**Important:** Only use Puttogether with card numbers you own or have permission to process.

---

## 📱 Example Workflow

Here's how to use Puttogether to extract card numbers from various sources:

### Scenario 1: Extract from a Receipt Photo

1. **Open the app** on your phone at https://puttogether.netlify.app
2. **Tap the Camera button** (📷) to take a photo of your receipt
3. **Wait for OCR processing** — You'll see progress as it scans the image (typically 10-30 seconds)
4. **View results** — Card numbers appear with their detected type (e.g., "Visa")
5. **Copy any card** by tapping the "Copy" button next to it
6. **Clear results** when done to remove all data from memory

### Scenario 2: Extract from a PDF Statement

1. **Open the app** on your computer or phone
2. **Drag and drop** your PDF file onto the drop zone, or click **Files & Downloads** (📁)
3. **Select your PDF** from your file picker
4. **Wait for processing** — The app extracts text from all pages
5. **Review extracted cards** — All valid card numbers are listed with their types
6. **Copy cards as needed** using the copy buttons
7. **Click Clear** to remove all results

### Scenario 3: Extract from Pasted Text

1. **Copy text** containing card numbers from any source (email, document, notes)
2. **Open Puttogether** in your browser
3. **Tap Notes & Paste Text** (📝)
4. **Paste your text** into the text area
5. **Tap "Extract Card Numbers"**
6. **View and copy** the extracted cards
7. **Clear results** when finished

### Scenario 4: Extract from Google Docs

1. **Open your Google Doc** on mobile or desktop
2. **Tap File → Download → Plain Text (.txt)** or **PDF Document**
3. **Return to Puttogether**
4. **Tap Files & Downloads** (📁)
5. **Select the downloaded file** from your Downloads folder
6. **View extracted cards**
7. **Copy and clear** as needed

---

## ✨ Features

### 📥 Multiple Input Methods

- **Files & Downloads** — Upload .txt, .csv, .pdf, .doc, .docx files
- **Photos & Gallery** — Select images from your device
- **Camera** — Capture photos directly (mobile only)
- **Notes & Paste Text** — Paste from clipboard or notes app
- **Google Docs** — Export and upload Google Docs
- **Google Drive** — Upload files from Google Drive
- **Drag & Drop** — Drag files onto the page (desktop)

### 🔄 Smart Processing

- **PDF text extraction** — Processes all pages automatically
- **Image OCR** — Optical character recognition for photos
- **Progress indicators** — Real-time status updates
- **Batch processing** — Upload multiple files at once
- **Format flexibility** — Handles various card number formats

### 📋 Results Management

- **Card type detection** — Identifies Visa, Mastercard, Amex, etc.
- **Clean formatting** — Numbers displayed in standard format
- **One-click copying** — Copy any card number instantly
- **Duplicate removal** — Automatically filters out repeated numbers
- **Clear function** — Instantly remove all results

---

## 🛠️ Technical Details

- **Technology**: Single-page HTML application with vanilla JavaScript
- **Dependencies**: PDF.js (v3.11.174), Tesseract.js (v4.1.1)
- **Browser Support**: All modern browsers (Chrome, Firefox, Safari, Edge)
- **Mobile Support**: Fully responsive, works on iOS and Android
- **Offline Capable**: Works offline after initial page load (requires cached libraries)
- **Deployment**: Static site hosted on Netlify

---

## 🚀 Use Cases

- **Personal Finance**: Extract card numbers from old statements or receipts
- **Document Organization**: Process archived financial documents
- **Data Migration**: Transfer card information between systems
- **Receipt Processing**: Extract payment information from photos
- **Accounting**: Batch process financial records
- **Testing**: Extract test card numbers from development documentation

---

## ⚠️ Disclaimer

Puttogether is designed for legitimate use with payment cards you own or have authorization to process. Users are responsible for:

- Only processing their own card numbers or those they have permission to access
- Complying with applicable privacy and data protection laws
- Securing their device and browser while using the app
- Clearing results when finished to prevent unauthorized access

While the app itself does not store or transmit data, users should take normal security precautions with their devices.

---

## 📄 License

This project is open source. Feel free to review the code and verify our privacy claims.

---

## 🤝 Contributing

Contributions are welcome! If you have suggestions for improvements or find issues:

1. Check the existing issues on GitHub
2. Open a new issue with detailed information
3. Submit a pull request with proposed changes

---

## 💬 Support

Having trouble? Check that:
- You're using a modern browser (Chrome, Firefox, Safari, Edge)
- JavaScript is enabled
- You have an internet connection (for initial load and library downloads)
- Your file format is supported (.txt, .pdf, .csv, .doc, .docx, images)

For bugs or feature requests, please open an issue on GitHub.

---

**Made with privacy in mind. Your data stays on your device, always.**
