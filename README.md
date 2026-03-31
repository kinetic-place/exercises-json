<p align="center">
  <a href="https://kinetic.place">
    <img src="https://kinetic.place/images/kinetic-logo-animated.gif" alt="Kinetic.place" width="400" />
  </a>
</p>

# 🏋️‍♂️ Kinetic Exercises (JSON)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![NPM Version](https://img.shields.io/npm/v/@kinetic-place/exercises-json)](https://npmjs.com/package/@kinetic-place/exercises-json)

An open-source JSON dataset containing **899+ structured fitness exercises**, complete with execution media, muscle mappings, and equipment requirements. Built and maintained by the Kinetic community.

👉 **[Get your free API Key at kinetic.place](https://kinetic.place)**

---

## 🚀 Why this dataset?

Building a fitness app is hard. Sourcing high-quality, standardized exercise data with video demonstrations shouldn't be. 

This repository provides the raw JSON files for developers who want to bundle the dataset directly into their React Native apps, NoSQL databases, or custom workflows.

**Want a zero-setup solution?**
If you prefer not to manage raw JSON files and media inside your frontend bundle, **[join the developer waitlist at kinetic.place](https://kinetic.place)**! We are launching a blazing-fast, edge CDN and REST API so you can fetch exercises instantly via API Key.

## 📦 Installation

```bash
npm install @kinetic-place/exercises-json
```
*Or download the `.json` files directly from the `/data` folder.*

## 📖 What's Included?
- **899+ Exercises**: Names, step-by-step instructions, and form cues.
- **Taxonomy**: Mapped specific target muscle groups, secondary muscles, and required equipment.
- **Images & Videos (Coming Soon)**: High-quality execution media loops (GIFs/MP4s) **created by real fitness content creators** are being added soon for every exercise, designed to be fully **brandable and customizable** for your app interface. **[Join the waitlist at kinetic.place](https://kinetic.place)** to get early API access to the premium media CDN!

*(Full documentation and schema examples coming closely...)*

## 🔌 Prefer an API?

See [`@kinetic-place/exercises-api`](https://github.com/kinetic-place/exercises-api) for a free REST API with **search, filtering, and pagination** — powered by Cloudflare Workers.

```bash
# Search exercises by muscle group
curl "https://api.kinetic.place/v1/exercises?muscle=chest&limit=5"

# Full-text search
curl "https://api.kinetic.place/v1/exercises?q=bench+press"

# Combined filters
curl "https://api.kinetic.place/v1/exercises?muscle=biceps&equipment=dumbbell&level=beginner"
```

## 🙏 Acknowledgments

A massive thank you to [wrkout/exercises.json](https://github.com/wrkout/exercises.json) for providing the foundational list of gym exercises that kickstarted this dataset!
