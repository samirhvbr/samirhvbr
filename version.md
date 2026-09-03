# Version — GitHub Profile — samirhvbr

**Current version:** `0.1.2`

GitHub profile README (@samirhvbr), terminal aesthetic.

> Working branch: **`main`**. What lives here shows up on the profile page, so a
> layout change is a public change — it earns the bump.

> This file is the **source of truth** for the project version: anything that needs
> to show or report the version extracts the **first semver number (`X.Y.Z`)** found
> here. Keep the **"Current version"** line as the first occurrence of a number.
>
> `0.1.0` marks the start of **versioning**, not the start of the project — whatever
> came before stays in the `git log`.

---

## 1. Versioning Convention (`X.Y.Z`)

| Component | Meaning | How it moves |
|---|---|---|
| **X** | Stable release | Manual |
| **Y** | Structural change — new section in the set, scope change, structural reorganization. | Manual |
| **Z** | Increment on every delivery (see triggers) | Every delivery |

### `Z` bump triggers

- Creating or removing a **document** from the set.
- Changing a **rule, decision or procedure** already published.
- Altering **structure or format** that another tool consumes.
- Adding or changing **data/examples** that serve as reference.

> Text fixes, comments and formatting do **not** require a bump.

---

## 2. Mandatory Commit Format

```
X.Y.Z - Short description in English
```

**Non-negotiable rules:**

1. The version **always** comes from this `version.md` — bump it **in the same commit**
   as the change.
2. Message in **English**, specific enough for `git log --grep`.
3. Conventional Commits (`feat:`, `fix:`, `chore:`…) and vague messages ("tweak",
   "update", "wip") are **forbidden**.
4. One objective per commit.

> **The COMMITTER skill commits for you in this repo** (there is a `.committer.yml`
> at the root). Write the changelog entry below when you finish the delivery: that is
> **where** the commit message comes from, at no model cost. Without the entry, the
> skill falls back to a path that burns tokens and describes the work worse than you
> would. Details in the PS block of `CLAUDE.md`.

---

## 3. Changelog

> Descending order (most recent on top).

### `0.1.2` — 2026-09-02 — Everything in English, including the commit convention

The profile README is the page a mostly international audience lands on, so it is now
written in English: the `fastfetch` block, the Mermaid ecosystem graph, the product
and open-source tables, `stack.toml` and the badge labels.

The convention docs follow the content: this `version.md` and the comments in
`.committer.yml` are in English too, and rule 2 of the commit format now reads
**English** instead of Portuguese. This repo deliberately diverges from the rest of
the fleet on commit language — the norm elsewhere stays Portuguese.

Also fixed: the `0.1.1` entry said the Releases follow "the `version.md` on **master**",
but the working branch here is **`main`** — `.committer.yml` pins `branch_only: main`.
The workflow already listened on both, so nothing was broken in practice; the text was.

_Triggers:_ published rule changed (commit language); format that another tool consumes
altered.

### `0.1.1` — 2026-09-02 — Automatic releases: the version.md on main becomes a tag and a Release

GitHub does not infer a version from a commit message: without a tag, the number is a
string in the `git log` and a `git diff` between versions does not exist. Enter
`.github/workflows/release.yml` and `tools/release.sh`.

**The rule:** the `version.md` on the default branch **on GitHub** is what the Releases
**on GitHub** reflect. A local checkout does not enter the calculation. A PR publishes
nothing; on merge, the push of `version.md` triggers the workflow and the Release
becomes that version.

Tag and title = the bare version, no `v` prefix. Norm:
[samirhvbr/repodocs](https://github.com/samirhvbr/repodocs/blob/master/docs/versioning.md).

### `0.1.0` — 2026-07-30 — Adopts the house versioning

Starts following the pattern of the other repositories: `version.md` as the source of
truth, commits in the `X.Y.Z - Description` format and a changelog as the delivery
record.

The trigger was practical: the repo already took part in the **COMMITTER** skill, but
without a `version.md` there was no house format — the cycle reported and did **not**
commit. With this file, the skill starts operating here through the deterministic path
(at no model cost), reading the message from the changelog entry.

_Triggers:_ adoption of versioning infrastructure.
