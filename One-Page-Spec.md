# Minimal Viable Creative File Taxonomy (MVCFT)

**v1.1 - one-page specification**

---

## 1. Design goals (non-negotiable)

This taxonomy must be:

* **Semiotically sound** (terms mean what humans already think they mean)
* **Software-agnostic**
* **Searchable on commodity OSes (Windows, macOS, Linux)**
* **Usable by teams, not just individuals**
* **Stable over decades**
* **Readable outside its original folder structure**
* **Free of ambiguous labels such as “final”, “new”, “latest”, etc.**

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

The domain field may contain additional descriptive words after the controlled domain term, joined with hyphens.

Examples:

```
Personal
Public-Graphic-Design
Client-Mueller-Brand
```

The first word must remain one of the controlled domain terms:
`Personal`, `Public`, or `Client`.

---

## 4. Naming schema (strict order)

```
YYYY-MM-DD_Domain_ObjectType_Context_Identifier_Qualifier_vNN.ext
```

### Separator rules

| Separator | Use                                  |
| --------- | ------------------------------------ |
| `_`       | separates major fields               |
| `-`       | separates words inside a field       |
| `.`       | reserved for the file extension only |

### Required fields

* `YYYY-MM-DD` → ISO date
* `Domain` → visibility, optionally extended with hyphenated descriptive words
* `ObjectType` → `File` / `Work` / `Asset`
* `Context` → project, theme, or functional grouping
* `Identifier` → human-readable, stable name
* `vNN` → zero-padded version number
* `ext` → actual file format

### Optional field

* `Qualifier` → medium, platform, encoding, variant, export target, or production state
  (never emotional states like “final”)

If no qualifier is needed, omit it rather than inserting filler text.

---

## 5. Context vs Identifier (important distinction)

### Context

* Groups related things
* Reused across many objects
* May describe a project, study area, campaign, experiment, or functional grouping
* Examples: `Illustration`, `Experiment`, `Sketch`, `Logo-Research`

### Identifier

* Names the thing itself
* Stable over time
* Should still make sense outside the original folder
* Examples: `CRTMelt`, `SecondTree`, `Horton-Strahler`

---

## 6. Dates

Dates are part of the canonical naming schema.

Format:

```
YYYY-MM-DD
```

Dates go **first** because this keeps files chronologically sortable in simple file browsers, ZIP archives, backup folders, and exported directory listings.

Use the date that is most meaningful for the object:

* creation date for original material
* publication date for published works
* delivery date for client deliveries
* scan date for scans
* export date for generated exports

Do not use vague date words such as:

* `today`
* `yesterday`
* `new`
* `recent`

---

## 7. Versioning

Versioning is allowed only in controlled form:

```
v01
v02
v03
```

Version numbers must be:

* zero-padded
* monotonic
* mechanical, not emotional
* placed before the file extension

Forbidden:

* `final`
* `final-final`
* `latest`
* `new`
* `v2-final`
* `really-final`

A released, printed, or delivered state should be expressed through the `Qualifier` field, not through emotional version labels.

Examples:

```
2026-06-16_Public_Work_Experiment_SecondTree_RGB_v01.png
2026-06-16_Client-Mueller-Brand_Work_Brand-Campaign_Hero-Visual_Print_v03.pdf
```

---

## 8. Canonical examples

### Asset

```
2026-06-16_Public_Asset_Experiment_CRTMelt_BSL_v01.bsl
```

### Editable file

```
2026-06-16_Personal_File_Experiment_SecondTree_BlackInk_v01.bkd
```

### Published illustration

```
2026-06-16_Public_Work_Experiment_SecondTree_RGB_v01.png
```

### Client delivery

```
2026-06-16_Client_Work_Brand-Campaign_Hero-Visual_Print_v01.pdf
```

### Public graphic-design research note

```
2026-06-16_Public-Graphic-Design_File_Toolmakers_Research-Notes_Source-List_v01.md
```

### Client logo asset

```
2026-06-16_Client-Mueller-Brand_Asset_Logo_Primary-Sign_SVG_v03.svg
```

---

## 9. Explicitly forbidden patterns

* ❌ `final`, `new`, `latest`, `really-final`
* ❌ unpadded versions such as `v2`
* ❌ software names as primary classifiers
* ❌ extra dots inside the filename
* ❌ spaces inside filenames
* ❌ mixed object types (`WorkFile`, `FinalAsset`)
* ❌ emotional or subjective qualifiers
* ❌ filenames that only make sense inside one folder
* ❌ names that differ only by letter case

---

## 10. Semantic invariants (must always hold)

* A **File** may produce Works
* A **Work** may be derived from Files
* An **Asset** never becomes a Work
* Exporting a File creates a **Work**, not another File
* Visibility does not change object type
* Versioning does not change object type
* File extension does not override semantic classification

---

## 11. Mental model (one sentence)

> **Files are for doing, Works are for showing, Assets are for making.**

---

Text edit finalized with chatgpt.com
