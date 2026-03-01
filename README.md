<div align="center">

# 📚 Memizy Open Library
**The Central Directory for OQSE Study Sets**

![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)
![Ecosystem](https://img.shields.io/badge/Ecosystem-Memizy-blueviolet?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

<br>

Welcome to the **Open Library**, the official community registry of study materials for the [Memizy Ecosystem](https://github.com/memizy/memizy).

</div>

---

## 🌍 Decentralized Architecture

To ensure maximum scalability and fast loading times, this repository **does not contain the actual study data or media files**. 

Instead, it operates on a decentralized "Polyrepo" model. This repository acts as a lightweight catalog directory, pointing to the actual `.oqse.json` files hosted in external GitHub repositories. 

When you browse the library in the Memizy app, it reads these catalogs to power the search and filter UI. The heavy content is downloaded directly from the creators' repositories via the global `jsDelivr` CDN only when a user requests it.

---

## 🏛️ The Tier System

To help users find high-quality and safe content, the library is divided into three registry files:

* **`official.json`**: Core study sets created, maintained, and guaranteed directly by the Memizy team.
* **`verified.json`**: High-quality community contributions that have been manually reviewed for factual accuracy, formatting, and structural integrity.
* **`community.json`**: The open frontier. Any valid OQSE submission starts here. These sets are available to everyone but come without official quality guarantees.

---

## 🚀 How to Add Your Study Set to the Library

Creating and sharing a set is completely free and requires no central approval, other than a basic structural check. All new submissions go directly into the Community tier.

### Step 1: Create your Repository
1. Create a new public GitHub repository for your study set (e.g., `my-anatomy-course`).
2. Write your study material according to the [OQSE Specification](https://github.com/memizy/oqse-specification).
3. Place your `data.oqse.json` file and any media `/assets` into your repository.

### Step 2: Submit to the Library
1. Fork this `open-library` repository.
2. Edit the **`community.json`** file and append a new object containing a projection of your set's metadata. 
3. Open a **Pull Request**.

*(Note: If your community set gains popularity and maintains high quality, the Memizy team may eventually promote it to the `verified.json` tier!)*

---

## 🛠️ Data Structure

Whether it is in the Official, Verified, or Community registry, the library expects a lightweight projection of the OQSE `meta` object. This allows the Memizy app to filter sets without downloading them.

```json
{
  "id": "Unique UUID matching your OQSE meta.id",
  "url": "Direct CDN link to the raw .oqse.json file",
  "title": "Name of your course",
  "description": "Short description for the library card",
  "author": "Your Name (extracted from PersonObject)",
  "subject": "e.g., Medicine, Law, Computer Science",
  "language": "en",
  "tags": ["keywords", "for", "search"],
  "updatedAt": "2024-01-15T08:30:00Z",
  "estimatedTime": 120,
  "requirements": {
    "features": ["math", "markdown"]
  }
}

```

*Note: The `requirements` object is crucial. It helps host applications verify compatibility before attempting to download the full study set.*

<div align="center">
<i>Maintained with ❤️ by the Memizy Team.</i>
</div>