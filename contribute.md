---
layout: default
title: Contribute
permalink: /contribute/
---
# Contributing to the Kei Truck, Van, and Car Manuals Project

Thank you for your interest in contributing! This project aims to recreate translated manuals for Kei vehicles as clean, accessible, web-based pages. Every contribution helps improve access to these resources for everyone world-wide.

We welcome contributions in the following areas:

---

## 🛠️ 1. Adding or Translating Manuals

You can contribute full or partial manuals in **Markdown (`.md`) format**.

### 📁 File Structure

Each manual is organized by:
```
manuals/Brand/Model/Year/Chassis/Manual-Section.md
```

**Example:**
```
manuals/Subaru/Sambar/2009/GBD-TT2/engine.md
```

Each manuals has its own /assets/ folder for manual-specific assets. Generic shared assets can be stored in the root /assets/ folder.

**Example:**
```
/assets/                            # Shared asset directory
│── images/
│   ├── /brand-logos                # Contains logos for all brands
/manuals/                           # Root manual directory
│── Subaru/                         # Car brand
│   ├── Sambar/                     # Car model
│   │   ├── 2009/                   # Year
│   │   │   ├── GBD-TT2/            # Chassis code
│   │   │   │   ├── index.md        # Lists all sections in GBD-TT2
│   │   │   │   ├── engine.md
│   │   │   │   ├── transmission.md
│   │   │   │   ├── electrical.md
│   │   │   │   ├── chassis.md
```

Each section file must include this **YAML front matter** at the top with the relevant metadata:

```yaml
---
layout: manual
title: "Engine Section"
brand: "Subaru"
model: "Sambar"
year: "2009"
chassis: "GBD-TT2"
---
```

### ✍️ Content Guidelines
- Use clear Markdown formatting (# for headings, - for lists, etc.)

- Store images and other assets in the manual's local assets folder. Use shared assets when applicable.

- Use a consistent language across the document(s) (translations are welcome).

- Link to other sections if relevant using relative paths.

## 🧪 2. Reviewing Existing Content
Help us improve accuracy and readability by:

- Uploading new manuals.

- Fixing typos or formatting issues.

- Adding missing sections to existing manuals.

- Improving structure, clarity, or grammar in translated text.

## 🧑‍💻 3. Enhancing the Site

You can also contribute by improving the Jekyll website itself:

- Fixing broken links.

- Improving accessibility and design.

- Adding search, breadcrumbs, or new features.

## 📦 4. How to Contribute

### 🔁 Fork the Repository

1. Click “Fork” on the main GitHub page.

2. Clone your fork:
```bash
git clone https://github.com/your-username/Kei-Truck-Van-and-Car-Manuals.git
cd Kei-Truck-Van-and-Car-Manuals
```

3. 🌱 Create a New Branch
```bash
git checkout -b add-sambar-tt2-engine
```

4. ✏️ Make Your Changes
Add or edit files, following the structure and style guidelines above.

5. ✅ Commit and Push
```bash
git add .
git commit -m "Add 2009 Subaru Sambar GBD-TT2 Engine section"
git push origin add-sambar-tt2-engine
```

6. 🚀 Create a Pull Request
Submit a PR to the main branch with a clear description of your changes or contributions.

## 📜 License and Credits

By submitting content, you confirm that you:

- Have permission to contribute (original or translated by you).

- Agree to license your contribution under the same open source terms as the project (GNU Public License).

Thank you for helping make this project possible!

— {{ site.author }}