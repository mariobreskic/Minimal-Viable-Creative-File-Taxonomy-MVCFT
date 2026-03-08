# Minimal-Viable-Creative-File-Taxonomy-MVCFT
This is a minimal, software-agnostic taxonomy to name creative things in a way that is searchable, team-safe, and semantically sound I use.

## About linguistic bugs in the system

### What the bug is

In the creative world, people often say **“work file”** and **“exported work”** almost interchangeably.

Examples:

* “Here’s the work file of my illustration” → they mean the `.bkd` / `.psd` master
* “Here’s the exported work” → they mean the `.png` / `.jpg` ready-to-publish image

**The problem:**

* **Both are called ‘work’ in casual speech**, but functionally they are different.
* OS, archives, and intelligent management need a **single source of truth**: *what is this file for?*

This confusion leads to filenames like:

```
20260127-workfile-second-tree.png
```

* You can’t tell: is it editable? reusable? meant for consumption?
* You have **mixed axes**: identity, type, and intent all mashed into one string.

That’s the “bug”: **language encourages ambiguity in naming**, which breaks search, categorization, and long-term archival.

---

### How my taxonomy fixes it

It separates **three dimensions clearly**:

| Axis   | Examples                                   | Notes                |
| ------ | ------------------------------------------ | -------------------- |
| Intent | Personal / Public / Client                 | Who the work is for  |
| Type   | File / Work / Asset                        | Function, not format |
| Domain | Illustration / Typography / Layout / Mixed | Category of work     |

So instead of ambiguous “work file,” we can now say:

```
Personal.File.Illustration.SecondTree.bkd
```

vs

```
Public.Work.Illustration.SecondTree.png
```

* **File** = editable master, kept for working in
* **Work** = expressive output, meant to be consumed
* **Asset** = reusable tool, meant to be applied in other works

Now every filename communicates the **function clearly**, not just “sounds like a work.”

---

#### Why this matters

* **Windows search** can immediately filter by Type → never accidentally grab a master when you want a published piece.
* **Metadata / Bridge** can store technique, brushes, dates, and provenance → richness without cluttering the filename.
* **Archives / long-term storage**: every item has a deterministic, unambiguous identity.

---

#### TL;DR

> The “linguistic bug” is: people call *everything* a “work file,” conflating **function** (File vs Work) with **intent** and **format**.
> This taxonomy fixes it by explicitly separating **Intent / Type / Domain / Identifier**, so the filename is *unambiguous*.


