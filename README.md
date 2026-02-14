# 🛢 Moroccan First Names Dataset

A simple and organized dataset of Moroccan first names.

It includes:

* English names (example: **Aya**, **Amine**)
* Arabic writing (example: **آية**, **أمين**)
* Short meanings
* Detailed meanings
* Full structured versions (all-in-one files)

This dataset is useful for:

* Signup forms
* Baby name apps
* Random name generators
* Learning Arabic
* Form validation
* Localization projects

---

## 📑 Table of Contents

- [📂 What Files Are Included?](#-what-files-are-included)
- [🚀 How To Use The Dataset](#-how-to-use-the-dataset)
- [💻 Simple Examples](#-simple-examples)
- [🎯 Which File Should You Use?](#-which-file-should-you-use)
- [🏷 Versioning Tip](#-versioning-tip)
- [⭐ Support](#-support)

---

# 📂 What Files Are Included?

## 1️⃣ Female Names (English)

### `female-first-names.json`

```json
{
  "names": [
    "Aya"
  ]
}
```

Contains only female names in English letters.

---

## 2️⃣ Male Names (English)

### `male-first-names.json`

```json
{
  "names": [
    "Amine"
  ]
}
```

Contains only male names in English letters.

---

## 3️⃣ Female Names (Arabic)

### `female-first-names-arabic.json`

```json
{
  "names": [
    "آية"
  ]
}
```

Contains female names written in Arabic.

---

## 4️⃣ Male Names (Arabic)

### `male-first-names-arabic.json`

```json
{
  "names": [
    "أمين"
  ]
}
```

Contains male names written in Arabic.

---

## 5️⃣ Female Names + Meaning

### `female-first-names-meanings.json`

```json
{
  "names": {
    "Aya": "miracle, sign, verse"
  }
}
```

---

## 6️⃣ Male Names + Meaning

### `male-first-names-meanings.json`

```json
{
  "names": {
    "Amine": "trustworthy, honest, faithful"
  }
}
```

---

## 7️⃣ Female Names + Extended Meaning

### `female-first-names-meanings-extended.json`

```json
{
  "names": {
    "Aya": "A name meaning a 'miracle', a 'sign from God', or a 'verse' of the Quran."
  }
}
```

---

## 8️⃣ Male Names + Extended Meaning

### `male-first-names-meanings-extended.json`

```json
{
  "names": {
    "Amine": "Refers to someone who is 'trustworthy', 'honest', or 'faithful'."
  }
}
```

---

## 9️⃣ Female All-In-One (Recommended)

### `female-first-names-all-in-one.json`

Everything in one place:

```json
{
  "names": {
    "Aya": {
      "in_arabic": "آية",
      "meaning": "miracle, sign, verse",
      "meaning_extended": "A name meaning a 'miracle', a 'sign from God', or a 'verse' of the Quran."
    }
  }
}
```

---

## 🔟 Male All-In-One (Recommended)

### `male-first-names-all-in-one.json`

```json
{
  "names": {
    "Amine": {
      "in_arabic": "أمين",
      "meaning": "trustworthy, honest, faithful",
      "meaning_extended": "Refers to someone who is 'trustworthy', 'honest', or 'faithful'."
    }
  }
}
```

---

# 🚀 How To Use The Dataset

You have 2 simple options:

---

# ✅ Option 1: Download The Files

1. Download the JSON files.
2. Put them inside your project.
3. Load them like any normal JSON file.

---

# ✅ Option 2: Use GitHub CDN (Recommended for Web Apps)

Example:

```
https://cdn.jsdelivr.net/gh/amine-amazou/moroccan-names-dataset@v1.0.0/male-first-names.json
```

Using a tag like `@v1.0.0` keeps your app stable.

---

# 💻 Simple Examples

---

## 🟨 JavaScript (Frontend Example)

Random female name suggestion for signup:

```javascript
async function randomName() {
  const res = await fetch(
    "https://cdn.jsdelivr.net/gh/amine-amazou/moroccan-names-dataset@v1.0.0/female-first-names.json"
  );
  
  const data = await res.json();
  const names = data.names;
  
  return names[Math.floor(Math.random() * names.length)];
}

randomName().then(console.log);
```

---

## 🟦 Node.js (Check If Name Exists)

```javascript
const data = require("./male-first-names.json");

function isValid(name) {
  return data.names.includes(name);
}

console.log(isValid("Amine")); // true
```

---

## 🟥 Python (Get Meaning)

```python
import json

with open("male-first-names-meanings.json", encoding="utf-8") as f:
    data = json.load(f)

print(data["names"].get("Amine")) # trustworthy, honest, faithful
```

---

## 🟩 PHP (Show Arabic Version)

```php
<?php
$data = json_decode(file_get_contents("male-first-names-all-in-one.json"), true);

echo $data["names"]["Amine"]["in_arabic"]; # أمين
?>
```

---

# 🎯 Which File Should You Use?

If you only need:

* Just names → use `*-first-names.json`
* Just arabic names → use `*-first-names-arabic.json`
* Names + meaning → use `*-meanings.json`
* Names + extended meaning → use `*-meanings-extended.json`
* Everything (best option) → use `*-all-in-one.json`

---

# 🏷 Versioning Tip

Always use a version tag like:

```
@v1.0.0
```

Instead of:

```
@main
```

This avoids breaking your app if the dataset changes.

---

# ⭐ Support

If this dataset helps you, consider giving it a star on GitHub.
