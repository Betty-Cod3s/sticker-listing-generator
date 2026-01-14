# Amazon Title Optimizer

**Bulk optimize Amazon product titles for better search visibility.**

A fast, privacy-first tool for optimizing inventory titles. Your data never leaves your browser.

---

## 🚀 Quick Start

1. **Open the tool** → Bookmark [your-url-here] for easy access
2. **Upload your inventory** → Drag & drop or click to browse (.csv or .xlsx)
3. **Select a strategy** → Choose OEM Premium, Compatible, or Universal Budget
4. **Generate titles** → Click the button, wait a few seconds
5. **Download** → Get your optimized file in the same format you uploaded

That's it. No accounts, no logins, no API keys.

---

## 📊 Input File Format

Your file should have these columns (flexible naming accepted):

| Column | Required | Accepted Names |
|--------|----------|----------------|
| SKU | ✓ | `sku`, `SKU`, `item_sku`, `ItemSKU` |
| Part Number | ✓ | `part_number`, `Part Number`, `PartNumber`, `part#`, `MPN` |
| Brand | ✓ | `brand`, `Brand`, `manufacturer` |
| Model | Optional | `model`, `Model`, `model_name` |
| Current Title | Optional | `current_title`, `title`, `item_name` |
| Price Tier | Optional | `price_tier`, `tier`, `Pricing` |

### Example Input:
```csv
SKU,Part Number,Brand,Model,Current Title,Price Tier
CEYBO-001,BN59-01178B,Samsung,UN55F6300,Samsung Remote,Premium
CEYBO-002,3026Q00T73,Onn,50" 4K,,Budget
```

---

## 📤 Output File Format

The tool adds three new columns to your file:

| New Column | Description |
|------------|-------------|
| `Optimized Title` | Your new Amazon-ready title |
| `Char Count` | Character count for the title |
| `Status` | ✅ Valid, ⚠️ Warning, ❌ Error |

### Example Output:
```csv
SKU,Part Number,Brand,Model,Optimized Title,Char Count,Status
CEYBO-001,BN59-01178B,Samsung,UN55F6300,"BN59-01178B Remote Control for Samsung UN55F6300 TV - OEM Replacement Compatible with Samsung Smart TV",108,✅
```

---

## 🎯 Optimization Strategies

### 1. OEM Premium (Part# First)
**Best for:** Known OEM parts, brand-loyal customers, premium pricing

```
BN59-01178B Remote Control for Samsung UN55F6300 TV - OEM Replacement Compatible with Samsung Smart TV
```

**Pattern:** `[PartNumber] Remote Control for [Brand] [Model] TV - OEM Replacement`

### 2. Compatible Mid-Range (Default)
**Best for:** Third-party replacements, mid-tier pricing, broad compatibility

```
Remote Control Compatible with Samsung UN55F6300 TV (BN59-01178B) - Universal Replacement for Smart TV
```

**Pattern:** `Remote Control Compatible with [Brand] [Model] TV ([PartNumber]) - Universal Replacement`

### 3. Universal Budget (Generic)
**Best for:** No-name products, budget pricing, maximum search reach

```
Universal TV Remote Control for Samsung UN55F6300 - Compatible Replacement BN59-01178B
```

**Pattern:** `Universal TV Remote Control for [Brand] [Model] - Compatible Replacement [PartNumber]`

---

## ⚙️ Options

### 🇲🇽 Include Spanish Keywords
Appends Spanish terms for bilingual search optimization:
```
Remote Control for Samsung TV | Control Remoto
```

### 📱 Mobile-Optimized
Prioritizes 150-character limit (mobile shows ~80 chars in search results). Titles are truncated at natural break points.

---

## ✅ Validation Rules

The tool automatically checks for:

| Rule | Status |
|------|--------|
| Title > 200 characters | ❌ Error |
| Title > 180 characters | ⚠️ Warning |
| Title < 60 characters | ⚠️ Warning |
| Prohibited terms (best, #1, free shipping) | ❌ Error |
| Special characters (<>{}[]) | ⚠️ Warning |

---

## 🔧 Technical Details

- **Zero dependencies** on external servers
- **Client-side only** — all processing happens in your browser
- **Privacy-first** — your inventory data never leaves your machine
- **Offline-capable** — works without internet after initial load
- **Libraries used:** Papa Parse (CSV), SheetJS (Excel)

---

## 📁 File Structure

```
amazon-title-optimizer/
├── index.html          # Main application (self-contained)
├── styles.css          # Styling (optional, embedded in HTML)
├── app.js              # Core logic (optional, embedded in HTML)
├── modules/            # Modular source files
│   ├── parser.js       # File parsing
│   ├── templates.js    # Title generation
│   ├── keywords.js     # Keyword banks
│   └── validator.js    # Validation rules
└── README.md           # This file
```

**Note:** The `index.html` file is fully self-contained and can be deployed standalone. The modular files are provided for reference and customization.

---

## 🚀 Deployment

### GitHub Pages (Recommended)
1. Push to GitHub repository
2. Go to Settings → Pages
3. Select `main` branch, `/root` folder
4. Your tool is live at `https://[username].github.io/amazon-title-optimizer/`

### Local Use
Simply open `index.html` in any modern browser.

---

## 📝 Changelog

### v1.0.0
- Initial release
- Three optimization strategies (OEM, Compatible, Universal)
- CSV and Excel support
- Spanish keyword option
- Mobile optimization option
- Validation with character counts

---

## 💡 Tips for Best Results

1. **Fill in all columns** — More data = better titles
2. **Use consistent model names** — "UN55F6300" not "Samsung 55 inch"
3. **Check part numbers** — These are your best keywords for OEM searches
4. **Review warnings** — Short titles may not compete well
5. **Test both strategies** — Different products may need different approaches

---

**Built with ☕ for CEYBO**
