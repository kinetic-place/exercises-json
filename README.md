<p align="center">
  <a href="https://kinetic.place">
    <img src="https://kinetic.place/images/kinetic-logo-animated.gif" alt="Kinetic.place" width="400" />
  </a>
</p>

# 🏋️‍♂️ Kinetic Exercises (JSON)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![NPM Version](https://img.shields.io/npm/v/@kinetic-place/exercises-json)](https://npmjs.com/package/@kinetic-place/exercises-json)

An open-source JSON dataset containing **899 structured fitness exercises**, complete with step-by-step instructions, muscle group mappings, and equipment requirements. Available in English and Spanish.

---

## 📦 Installation

```bash
npm install @kinetic-place/exercises-json
```

Or download the `.json` files directly from the `en/` and `es/` folders.

## 📂 What's Included

```
exercises-json/
├── en/
│   └── exercises.json    # 899 exercises (English)
└── es/
    └── exercises.json    # 899 exercises (Spanish)
```

Each file is a **single flat JSON array** — no configuration, no parsing, just import and go.

## 🚀 Quick Start

### JavaScript / TypeScript

```typescript
import exercises from '@kinetic-place/exercises-json/en/exercises.json';

console.log(exercises.length); // 899

// Find all chest exercises
const chestExercises = exercises.filter(ex =>
  ex.muscleGroups.some(mg => mg.slug === 'chest' && mg.type === 'primary')
);

// Find dumbbell exercises for beginners
const beginnerDumbbell = exercises.filter(ex =>
  ex.difficultyLevel === 'beginner' &&
  ex.equipment.some(eq => eq.name === 'Dumbbell')
);
```

### Python

```python
import json

with open('node_modules/@kinetic-place/exercises-json/en/exercises.json') as f:
    exercises = json.load(f)

# Group by category
from collections import Counter
categories = Counter(ex['category'] for ex in exercises)
print(categories)
# Counter({'strength': 742, 'stretching': 60, 'cardio': 38, ...})
```

### React Native / Mobile

```typescript
// Bundle directly — no API calls needed
const exercises = require('@kinetic-place/exercises-json/en/exercises.json');

// Use in your workout builder
const exercise = exercises.find(ex => ex.name === 'Barbell Bench Press');
```

## 📖 Data Schema

Each exercise object has the following structure:

```json
{
  "id": "d586b5aa-c2f4-4cb5-8038-d10b03c3b763",
  "name": "Barbell Bench Press",
  "type": "reps",
  "difficultyLevel": "intermediate",
  "forceType": "push",
  "mechanics": "compound",
  "category": "strength",
  "instructions": [
    "Lie flat on a bench with your feet planted firmly on the floor...",
    "As you breathe in, slowly lower the bar to your mid-chest..."
  ],
  "muscleGroups": [
    { "id": "...", "slug": "chest", "name": "Chest", "type": "primary" },
    { "id": "...", "slug": "triceps", "name": "Triceps", "type": "primary" }
  ],
  "equipment": [
    { "id": "...", "name": "Barbell", "type": "weight", "usageType": "single", "numItems": null }
  ]
}
```

### Field Reference

| Field | Type | Description |
|-------|------|-------------|
| `id` | `string` | UUID — stable across versions |
| `name` | `string` | Exercise name (localized) |
| `type` | `string` | Measurement type: `reps`, `time`, or `distance` |
| `difficultyLevel` | `string \| null` | `beginner`, `intermediate`, or `expert` |
| `forceType` | `string \| null` | Primary force: `push`, `pull`, or `static` |
| `mechanics` | `string \| null` | Movement type: `compound` or `isolation` |
| `category` | `string \| null` | Exercise category (see values below) |
| `instructions` | `string[]` | Step-by-step coaching cues |
| `muscleGroups` | `MuscleGroup[]` | Muscles targeted (see below) |
| `equipment` | `Equipment[]` | Required equipment (see below) |

### Categories

`strength` · `stretching` · `cardio` · `plyometrics` · `powerlifting` · `olympicWeightlifting` · `strongman`

### Difficulty Levels

`beginner` · `intermediate` · `expert`

### Muscle Group Object

| Field | Type | Description |
|-------|------|-------------|
| `id` | `string` | UUID |
| `slug` | `string` | URL-safe identifier (e.g., `chest`, `biceps`) |
| `name` | `string` | Display name (e.g., `Chest`, `Biceps`) |
| `type` | `string` | Targeting: `primary`, `secondary`, or `tertiary` |

**17 muscle groups**: abdominals · abductors · adductors · biceps · calves · chest · forearms · glutes · hamstrings · lats · lower back · middle back · neck · quadriceps · shoulders · traps · triceps

### Equipment Object

| Field | Type | Description |
|-------|------|-------------|
| `id` | `string` | UUID |
| `name` | `string` | Equipment name (e.g., `Barbell`, `Dumbbell`) |
| `type` | `string` | `weight` or `resistance` |
| `usageType` | `string \| null` | `single`, `double`, or `multiple` |
| `numItems` | `number \| null` | Number of items needed (if applicable) |

**36 equipment types** including: Barbell · Dumbbell · Cable · Machine · Body Only · Kettlebell · Bands · Medicine Ball · Exercise Ball · and more.

## 🌐 Locales

| Language | Path | Status |
|----------|------|--------|
| English | `en/exercises.json` | ✅ Complete (899) |
| Spanish | `es/exercises.json` | ✅ Complete (899) |

## 🔌 Prefer an API?

If you'd rather fetch exercises on demand instead of bundling the JSON, use the free REST API:

```bash
# Search exercises by muscle group
curl "https://api.kinetic.place/v1/exercises?muscle=chest&limit=5"

# Full-text search
curl "https://api.kinetic.place/v1/exercises?q=bench+press"

# Combined filters
curl "https://api.kinetic.place/v1/exercises?muscle=biceps&equipment=dumbbell&level=beginner"
```

See [`@kinetic-place/exercises-api`](https://github.com/kinetic-place/exercises-api) for self-hosting, or use the free hosted instance at `https://api.kinetic.place`.

## Related Packages

| Package | Description |
|---------|-------------|
| [`@kinetic-place/exercises-db`](https://github.com/kinetic-place/exercises-db) | Database-ready format with separate entity files |
| [`@kinetic-place/exercises-api`](https://github.com/kinetic-place/exercises-api) | Self-hostable REST API with search + filtering |

## 🙏 Acknowledgments

A massive thank you to [wrkout/exercises.json](https://github.com/wrkout/exercises.json) for providing the foundational list of gym exercises that kickstarted this dataset!

## License

MIT © [Kinetic.place](https://kinetic.place)
