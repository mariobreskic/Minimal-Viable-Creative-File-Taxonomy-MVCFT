# Minimal Viable Creative File Taxonomy (MVCFT)

**v1.0 - one-page specification**

---

## 1. Design goals (non-negotiable)

This taxonomy must be:

* **Semiotically sound** (terms mean what humans already think they mean)
* **Software-agnostic**
* **Searchable on commodity OSes (Windows, macOS, Linux)**
* **Usable by teams, not just individuals**
* **Stable over decades**
* **Free of “final”, “v2”, “latest”, etc.**

---

## 2. Core object types (closed set)

Exactly **three** first-class object types exist.

### 2.1 File

> A manipulable container used in a process of production.

* Editable
* Process-oriented
* May generate works
* Not primarily for presentation

Examples:
`psd`, `bkd`, `ai`, `indd`, `blend`, `aep`

---

### 2.2 Work

> A discrete expressive artifact intended for presentation or consumption.

* Experience-oriented
* Self-contained
* Does not require internal structure access
* May exist in multiple encodings

Examples:
`jpg`, `png`, `pdf (read-only)`, `mp4`, `gif`, `wav`

---

### 2.3 Asset

> A reusable instrument used to create or modify works or files.

* Reusable
* Not a finished expression
* Tooling, not outcome

Examples:
`brush`, `texture`, `shader`, `lut`, `font`, `pattern`

---

## 3. Visibility domain (controlled vocabulary)

Visibility is **orthogonal** to object type.

| Domain   | Meaning                                     |
| -------- | ------------------------------------------- |
| Personal | Private, exploratory, unpublished           |
| Public   | Published, shared, or intentionally exposed |
| Client   | Commissioned or contract-bound              |

Exactly **one** domain per object.

---

## 4. Naming schema (strict order)

```
Domain.ObjectType.Context.Identifier[.Qualifier].Extension
```

### Required fields

* `Domain` → visibility
* `ObjectType` → File / Work / Asset
* `Context` → project, theme, or functional grouping
* `Identifier` → human-readable, stable name
* `Extension` → actual file format

### Optional

* `Qualifier` → medium, platform, encoding, or variant
  (never emotional states like “final”)

---

## 5. Context vs Identifier (important distinction)

### Context

* Groups related things
* Reused across many objects
* Examples: `Illustration`, `Experiment`, `Sketch`

### Identifier

* Names the thing itself
* Stable over time
* Examples: `CRTMelt`, `SecondTree`, `HortonStrahler`

---

## 6. Dates (explicitly optional)

Dates are **not part of the core taxonomy**.

Allowed **only** if:

* the date is semantically meaningful (e.g. daily generative output)
* or required for external systems

Format (if used):

```
YYYYMMDD
```

Dates go **after Identifier**, never before.

---

## 7. Canonical examples (these are my own files)

### Asset

```
Public.Asset.Experiment.CRTMelt.BSL.bsl
```

### Editable file

```
Personal.File.Experiment.SecondTree.BlackInk.bkd
```

### Published illustration

```
Public.Work.Experiment.SecondTree.RGB.png
```

### Client delivery

```
Client.Work.BrandCampaign.HeroVisual.Print.pdf
```

---

## 8. Explicitly forbidden patterns

* ❌ `final`, `v2`, `new`, `latest`
* ❌ software names as primary classifiers
* ❌ dates as leading identifiers
* ❌ mixed object types (`WorkFile`, `FinalAsset`)
* ❌ emotional or subjective qualifiers

---

## 9. Semantic invariants (must always hold)

* A **File** may produce Works
* A **Work** may be derived from Files
* An **Asset** never becomes a Work
* Exporting a File creates a **Work**, not another File
* Visibility does not change object type

---

## 10. Mental model (one sentence)

> **Files are for doing, Works are for showing, Assets are for making.**


