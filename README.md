<div align="center">

# 📚 Memizy Open Library
**The Central Directory for OQSE Study Sets**

![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)
![Ecosystem](https://img.shields.io/badge/Ecosystem-Memizy-blueviolet?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

<br>

Welcome to the **Open Library**, the official community registry of study materials for the [Memizy Ecosystem](https://github.com/memizy/memizy).

<br>

[![Community Sets](https://img.shields.io/badge/JSON-Community-orange?style=for-the-badge&logo=json)](https://cdn.jsdelivr.net/gh/memizy/open-library@main/community.json)
[![Official Sets](https://img.shields.io/badge/JSON-Official-blue?style=for-the-badge&logo=json)](https://cdn.jsdelivr.net/gh/memizy/open-library@main/official.json)
[![Verified Sets](https://img.shields.io/badge/JSON-Verified-green?style=for-the-badge&logo=json)](https://cdn.jsdelivr.net/gh/memizy/open-library@main/verified.json)

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
2. Edit the **`community.json`** file and append a new object representing your set's metadata. 
3. Open a **Pull Request**.

*(Note: If your community set gains popularity and maintains high quality, the Memizy team may eventually promote it to the `verified.json` tier!)*

---

## 🛠️ Data Structure (OQSEH)

Whether it is in the Official, Verified, or Community registry, the library uses the **OQSEH (Open Quiz & Study Exchange Header)** standard. 

This is a lightweight projection of the full OQSE `meta` object combined with a direct CDN URL. This standard allows the Memizy app to quickly load library cards, search, and filter sets without having to download the heavy content first.

> **💡 Tip for GitHub Links:** When setting the `url` field for a set hosted on GitHub, we highly recommend using the **jsDelivr CDN** (e.g., `https://cdn.jsdelivr.net/gh/user/repo@main/...`) rather than standard raw GitHub links. This ensures fast, reliable, and production-ready global delivery.

```json
{
  "$schema": "https://cdn.jsdelivr.net/gh/memizy/oqse-specification@main/schemas/oqse-header-v0.1.json",
  "id": "123e4567-e89b-12d3-a456-426614174000",
  "url": "https://cdn.jsdelivr.net/gh/your-username/your-repo@main/data.oqse.json",
  "title": "Name of your course",
  "description": "Short description for the library card.",
  "author": {
    "name": "Your Name"
  },
  "subject": "Computer Science",
  "language": "en",
  "tags": ["keywords", "for", "search"],
  "updatedAt": "2024-01-15T08:30:00Z",
  "estimatedTime": 120,
  "requirements": {
    "features": ["math", "markdown"]
  }
}