# Minimal Viable Creative File Taxonomy (MVCFT)

This is a minimal, software-agnostic taxonomy for naming creative files in a way that is searchable, team-safe, semantically sound, and durable across operating systems, archives, and long-term storage.

The current canonical filename structure is:

```text
YYYY-MM-DD_Domain_ObjectType_Context_Identifier_Qualifier_vNN.ext
```

Separator logic:

```text
_   separates major fields
-   separates words inside a field
.   is reserved for the file extension
```

Example:

```text
2026-06-16_Public_Work_Illustration_SecondTree_RGB_v01.png
```

---

## About linguistic bugs in the system

### What the bug is

In the creative world, people often say **“work file”** and **“exported work”** almost interchangeably.

Examples:

* “Here’s the work file of my illustration” → they mean the `.bkd` / `.psd` / `.ai` master file
* “Here’s the exported work” → they mean the `.png` / `.jpg` / `.pdf` ready-to-publish output

**The problem:**

* **Both are called “work” in casual speech**, but functionally they are different.
* Operating systems, archives, teams, and asset-management systems need a **single source of truth**: *what is this file for?*

This confusion leads to filenames like:

```text
20260127-workfile-second-tree.png
```

The filename does not clearly say whether the object is:

* editable
* reusable
* meant for presentation
* meant for publication
* only an export
* only a working file

It mixes identity, type, intent, date, and format into one ambiguous string.

That is the “bug”: **ordinary language encourages ambiguity in naming**, and that ambiguity breaks search, categorization, handover, and long-term archival.

---

## How MVCFT fixes it

MVCFT separates the relevant dimensions clearly:

| Field        | Examples                                             | Meaning                                             |
| ------------ | ---------------------------------------------------- | --------------------------------------------------- |
| `Date`       | `2026-06-16`                                         | Chronological anchor                                |
| `Domain`     | `Personal`, `Public`, `Client`                       | Visibility or ownership context                     |
| `ObjectType` | `File`, `Work`, `Asset`                              | Function, not format                                |
| `Context`    | `Illustration`, `Typography`, `Layout`, `Experiment` | Project, theme, or functional grouping              |
| `Identifier` | `SecondTree`, `CRTMelt`, `Horton-Strahler`           | Stable human-readable name                          |
| `Qualifier`  | `RGB`, `Print`, `BlackInk`, `SVG`                    | Medium, variant, export target, or production state |
| `Version`    | `v01`, `v02`, `v03`                                  | Controlled mechanical versioning                    |
| `Extension`  | `.bkd`, `.psd`, `.png`, `.pdf`                       | Actual file format                                  |

So instead of ambiguous “work file,” we can now say:

```text
2026-06-16_Personal_File_Illustration_SecondTree_BlackInk_v01.bkd
```

vs.

```text
2026-06-16_Public_Work_Illustration_SecondTree_RGB_v01.png
```

vs.

```text
2026-06-16_Public_Asset_Experiment_CRTMelt_BSL_v01.bsl
```

In this system:

* **File** = editable master, kept for working in
* **Work** = expressive output, meant to be seen, read, watched, heard, or otherwise consumed
* **Asset** = reusable tool or component, meant to be applied in other files or works

Now every filename communicates the **function of the object**, not merely what it vaguely “sounds like.”

---

## Why this matters

* **Search becomes safer:** filtering for `_File_`, `_Work_`, or `_Asset_` immediately narrows the result by function.
* **Teams can exchange files without guessing:** the filename already explains whether something is editable, publishable, or reusable.
* **Archives become more stable:** each item keeps a readable identity even outside its original folder.
* **Metadata can stay metadata:** technique, provenance, notes, brushes, and production details can live in Bridge, sidecars, manifests, or documentation without overloading the filename.
* **The extension remains honest:** the final dot belongs only to the actual file format.

---

## Forbidden patterns

Avoid:

```text
final
final-final
new
latest
v2-final
really-final
```

Avoid extra dots inside the filename:

```text
Public.Work.Illustration.SecondTree.RGB.v01.png
```

Prefer underscores and hyphens:

```text
2026-06-16_Public_Work_Illustration_SecondTree_RGB_v01.png
```

---

## TL;DR

> The “linguistic bug” is that people call too many different creative objects a “work file,” conflating **function**, **visibility**, **format**, and **intent**.
>
> MVCFT fixes this by separating `Date`, `Domain`, `ObjectType`, `Context`, `Identifier`, `Qualifier`, `Version`, and `Extension`, so the filename remains unambiguous, searchable, and durable.

Text edit finalized with chatgpt.com
