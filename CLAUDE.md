# Project purpose

This repo doubles as an Obsidian vault for capturing and developing ideas
through conversation. The user talks through an idea; Claude elaborates it
into a proper note and files it in the vault, then keeps the vault's hub
note up to date so everything stays reachable by links.

This is on top of (not a replacement for) the repo's other purpose as the
Obsidian Sample Plugin scaffold (`main.ts`, `manifest.json`, etc.) — the
vault content and the plugin code live side by side and don't interact.

# Vault structure

- `notes/` — one Markdown file per idea/topic.
- `Home.md` — the hub note. Every note in `notes/` must be linked from here.

# Workflow: when the user shares an idea

1. **Elaborate, don't transcribe.** Take what the user says and write it up
   as a real note: clear title, organized sections, expand on implications
   or open questions where useful. Don't just paste their message verbatim.
2. **File name**: Title Case matching the note's `# Heading`, saved as
   `notes/<Title Case Name>.md`. Spaces are fine (Obsidian handles them).
3. **Frontmatter** at the top of every note:
   ```yaml
   ---
   created: <YYYY-MM-DD>
   tags: []
   ---
   ```
4. **Link liberally.** Use Obsidian wikilinks (`[[Note Name]]`) to connect
   a new note to existing related notes, and add a reciprocal link back
   from those existing notes if it makes sense.
5. **Update `Home.md` immediately** — every time a note is added, renamed,
   or removed, update `Home.md` in the same turn so its links never go
   stale. Group links under topical headings (create a new heading if the
   note doesn't fit an existing one); don't just append to a flat list.
6. Don't ask permission to create/edit notes or update `Home.md` — that's
   the expected behavior on every new idea. Do check in if an idea is too
   thin to turn into a standalone note (suggest folding it into an
   existing one instead).

# Conventions

- Keep notes atomic: one idea/topic per note. Split a note that's grown
  into multiple unrelated topics rather than letting it sprawl.
- Prefer linking to a related note over duplicating its content.
- No comments-about-the-process inside notes (e.g. "Claude added this on
  ...") — notes should read as the user's own knowledge base.
