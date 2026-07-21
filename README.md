# Threadbook

**A no-bullshit Obsidian vault for writing, linking, and moving on.**

<p>
  <img alt="Plain Markdown" src="https://img.shields.io/badge/notes-Markdown-111827?style=for-the-badge&logo=markdown&logoColor=white">
  <img alt="Local Only" src="https://img.shields.io/badge/storage-Local--Only-5c8af5?style=for-the-badge">
  <img alt="No housekeeping" src="https://img.shields.io/badge/housekeeping-None-16a34a?style=for-the-badge">
  <img alt="Flat structure" src="https://img.shields.io/badge/structure-Flat-f59e0b?style=for-the-badge">
</p>

Threadbook removes note maintenance from note-taking. There are no categories to manage, frontmatter forms to complete, mandatory tags to remember, or nested folders to reorganize. No framework—whether [Johnny Decimal](https://johnnydecimal.com/), [Zettelkasten](https://zettelkasten.de/), or [PARA](https://www.buildingasecondbrain.com/para)—is required.

> [!TIP]
> **Open → write → link when useful → search when needed.** That is the entire system.

## The workflow

- Every day begins with one Markdown file in `Diary`. Write directly in it.
- If an idea needs room, type a wikilink such as `[[Useful idea]]` and open it.
- Obsidian creates `Notes/Useful idea.md`; write there and leave it there.

> [!NOTE]
> No filing step follows. Wikilinks preserve context, and search retrieves the note later. This stays the same whether the vault contains ten notes or ten thousand.

## Get started

### 1. Create your Threadbook

<p>
  <a href="https://github.com/HYP3R00T/Threadbook/generate">
    <img alt="Use this template" src="https://img.shields.io/badge/Use_this_template-Create_your_Threadbook-2ea44f?style=for-the-badge&logo=github&logoColor=white">
  </a>
</p>

The recommended setup is to create an independent repository from this template:

1. Select **Use this template → Create a new repository**.
2. Choose an owner, repository name, and visibility.
3. Select **Create repository**.
4. Clone **your newly created repository**, not the original Threadbook repository.

```powershell
git clone https://github.com/YOUR-USERNAME/YOUR-THREADBOOK.git
```

Your copy starts with the complete Threadbook structure and configuration, but it has its own Git history and remote. You can customize and push it without sending changes back to this repository.

> [!NOTE]
> Prefer not to use Git? Select **Code → Download ZIP**, extract it, and open the extracted folder in Obsidian. You can start writing without creating a GitHub repository.

### 2. Open the vault

Install [Obsidian](https://obsidian.md/download), select **Open folder as vault**, and choose the cloned `Threadbook` folder.

### 3. Install the plugins

Open **Settings → Community plugins**, review the plugins below, turn off Restricted Mode, and install them. Reload Obsidian when finished.

> [!IMPORTANT]
> Plugin executables are not stored in this repository. Install them from their original sources so Obsidian can manage updates normally.

| Plugin | Purpose |
| --- | --- |
| [Hide Folders](https://github.com/jonasdoesthings/obsidian-hide-folders) | Keeps supporting folders such as `Extras` out of sight. |
| [Sort and Permute Lines](https://github.com/vinzent03/obsidian-sort-and-permute-lines) | Sorts, reverses, or shuffles selected lines and headings. |
| [Linter](https://github.com/platers/obsidian-linter) | Keeps Markdown formatting consistent on save. |
| [Templater](https://github.com/silentvoid13/Templater) | Creates date navigation and positions the writing cursor. |
| [CFR Find](https://github.com/cferrugem/obsidian-cfr-find) | Provides fast, typo-tolerant local vault search. |

The first four plugins are available through Obsidian's Community plugins browser. CFR Find currently requires manual installation: obtain `main.js`, `manifest.json`, and `styles.css` from its repository, place them in `.obsidian/plugins/cfr-find/`, reload Obsidian, and enable the plugin.

Only run plugins and templates you trust. Templater supports JavaScript and optional system commands; system commands are disabled in Threadbook's supplied configuration.

### 4. Start writing

Open today's note with `Ctrl+D`, or restart the vault and let today's note open automatically. The template adds links to yesterday and tomorrow:

```markdown
[[2026-07-19]] | [[2026-07-21]]

---

# Logs
```

## What is included

```text
Threadbook/
├── Diary/                    private daily notes
├── Notes/                    private ordinary notes
├── Extras/
│   └── Templates/            reusable note templates
├── .obsidian/                shared Obsidian configuration
├── .gitignore                privacy boundary
└── README.md
```

| Behaviour | Threadbook default |
| --- | --- |
| Vault startup | Open today's daily note |
| Daily notes | `Diary/YYYY-MM-DD.md` |
| New linked notes | Flat `Notes` folder |
| Note format | Plain Markdown |
| Required metadata | None |
| Retrieval | Wikilinks and CFR Find |

## Shortcuts

| Action | Windows / Linux | macOS |
| --- | --- | --- |
| Open today's daily note | `Ctrl+D` | `Command+D` |
| Search with CFR Find | `Ctrl+Alt+F` | `Command+Option+F` |
| Open the command palette | `Ctrl+P` | `Command+P` |
| Toggle the left sidebar | `Ctrl+Shift+B` | `Command+Shift+B` |

<details>
<summary><strong>Templates and appearance</strong></summary>

Templates live in `Extras/Templates`:

- `daily_notes_template.md` adds previous/next date links and the `Logs` heading.
- `notes_template.md` creates a titled ordinary note and places the cursor.

The included CSS snippets are configured in `.obsidian/snippets`. If they are not active after opening the vault, enable them under **Settings → Appearance → CSS snippets**.

The appearance configuration references **FiraCode Nerd Font Mono**. Obsidian uses an available fallback font when it is not installed.

</details>

## Private notes, public structure

```text
GitHub                       Private storage
──────────────────────       ──────────────────────
settings                     Diary/
templates                    Notes/
CSS snippets                 Attachments/
documentation                deleted notes
```

Git ignores the contents of `Diary`, `Notes`, `Attachments`, and `.trash`, along with workspace state, caches, and downloaded plugin executables. The reusable structure remains suitable for GitHub while personal writing can be synchronized through Proton Drive or another private provider.

> [!WARNING]
> The privacy boundary is folder-based. A private note created in the vault root or under `Extras` can appear in Git. Review `git status` before every public commit.

```powershell
git status --short
git diff --cached
```

Git distributes the structure; it is not the backup for private notes. Avoid editing the same note simultaneously on multiple devices, and let private synchronization finish before switching devices.

## Make it yours

Everything is ordinary Markdown and ordinary Obsidian configuration. Change the templates, shortcuts, plugins, or appearance freely. If you rename a private-content folder, update `.gitignore` before putting notes inside it.

## Support Threadbook

If Threadbook saves you time, you can support its maintenance and future improvements through GitHub Sponsors.

<p>
  <a href="https://github.com/sponsors/HYP3R00T">
    <img alt="Sponsor HYP3R00T on GitHub" src="https://img.shields.io/badge/Sponsor_on_GitHub-Support_Threadbook-ea4aaa?style=for-the-badge&logo=githubsponsors&logoColor=white">
  </a>
</p>

---

Made with ♥️ for people who would rather write than organize. 
