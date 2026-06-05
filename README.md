# QR 標籤產生器

A modern, single-page web application for batch generating QR code labels for construction sites. Built for **Eagle AI**, this tool streamlines the creation of A4 construction site labels with customizable floor and room information.

## 🎯 Features

- **Batch QR Code Generation** - Generate multiple QR codes in bulk with different floor and room combinations
- **Flexible Selection** - Choose from 22 floor levels (FND through 15F) and 10 room types
- **Multiple Export Formats**
  - 📄 **PDF/Print** - A4-sized labels optimized for printing (150mm × 150mm QR codes)
  - 📦 **PNG ZIP** - Export all QR codes as individual PNG images in a zip file
- **Live Preview** - See up to 16 QR code previews before generating
- **Progress Tracking** - Real-time progress bar during batch operations
- **Construction Metadata** - Embed construction ID and name in each QR code
- **Responsive Design** - Works seamlessly on desktop and mobile devices

## 🚀 Quick Start

1. **Open in Browser**
   ```
   Open `index.html` directly in any modern web browser
   ```

2. **Configure Project Info**
   - Enter **Construction ID** (e.g., `3518b017-3160-4f58-b514-c953d6af88b3`)
   - Enter **Construction Name** (e.g., `大同案`)

3. **Select Floors & Rooms**
   - Click checkboxes to select desired floors (B5, B4, etc.) and rooms (A1, A2, etc.)
   - Use "全選" (Select All) and "清除" (Clear) buttons for quick selection
   - Preview shows label count and sample QR codes

4. **Export**
   - **列印 / 儲存 PDF** - Opens print dialog to save as PDF or print directly
   - **下載全部 PNG (ZIP)** - Downloads all QR codes as PNG files in a zip archive

## 📋 Available Options

### Floors (樓層)
FND, B5, B4, B3, B2, B1, 1F–15F, RF (22 total)

### Rooms (房間)
- 公共區域 (Common Area)
- 全樓層 (Full Floor)
- A1–A3, A5–A8, A11 (Unit Rooms)

## 🛠️ Technical Details

### Dependencies
- **QR Code Generation**: [qr-creator](https://www.npmjs.com/package/qr-creator) v1.0.0
- **ZIP File Creation**: [jszip](https://stuk.github.io/jszip/) v3.10.1
- **Fonts**: Google Fonts (Noto Sans TC, JetBrains Mono)

### QR Code Payload
Each QR code encodes a JSON payload:
```json
{
  "constructionId": "3518b017-3160-4f58-b514-c953d6af88b3",
  "constructionName": "大同案",
  "floor": "1F",
  "room": "A1"
}
```

### Label Specifications
- **Print Format**: A4 (210mm × 297mm per page)
- **QR Code Size**: 150mm × 150mm (print), 70px (preview)
- **Error Correction**: Medium (M)
- **File Format**: PNG (transparent background, white fill)

## 📐 Color Scheme
- Background: `#f5f4f0`
- Surface: `#ffffff`
- Text: `#1a1917`
- Accent: `#1a1917` (dark)
- Borders: `#e2e0d8`

## 🌐 Browser Support
- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Any browser supporting:
  - HTML5 Canvas
  - Fetch API
  - ES6 JavaScript

## 📦 Export Details

### PDF/Print Output
- One label per A4 page
- Automatically scales QR code to 150mm × 150mm
- Displays construction name, floor, and room
- Ready for direct printing or PDF export

### PNG ZIP Output
- Individual PNG files for each floor/room combination
- High resolution (1240 × 1754 pixels)
- Filenames: `{floor}_{room}.png` (e.g., `1F_A1.png`)
- All files packaged in a single ZIP file

## ⌨️ Keyboard & UI
- Click chips (tags) to toggle floor/room selection
- Use select/clear buttons for bulk operations
- Progress indicator during batch operations
- Button auto-disable when no selections made

## 📄 License
Internal use only - Eagle AI

## 👨‍💻 Author
Created for **Eagle AI** construction site labeling system
