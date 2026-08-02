<p align="center">
  <img src="assets/second-brain-template-icon.png" alt="Second Brain template icon" width="240">
</p>

# Second Brain Template

This is a lightweight, file-based starter for creating a private-by-default second
brain for anyone. It gives AI assistants and humans one place for personal context,
current priorities, projects, and durable knowledge without requiring a database or
paid service.

Personal setup files are local-only by default. That matters because this repository
is currently public.

## Quick Start

No developer tools are required for the recommended setup.

1. Download the folder from GitHub or clone it if you already use Git.
2. Rename the folder for its new owner, then open it in Codex or another file-aware
   AI assistant.
3. Say: **“Set up this second brain with me.”**

The assistant will begin a short conversation about what the second brain should be
called, what matters to you, how you want to work together, your current priorities,
and your privacy boundaries. When image generation is available, it will also create
a transparent, expressive 3D character icon in the same visual family as the template
mascot. After approval, it will offer to turn that character into an animated Codex
pet. It will show you a summary before creating files, then help you complete one
useful starter task. It should not ask you to install Node.js, npm, Git, or Obsidian.

After setup, open `Dashboard.md` in any Markdown editor. The folder can also be opened
as an [Obsidian](https://obsidian.md/) vault, but Obsidian is optional and is not the
end of the setup process.

## Optional Terminal Setup

People who prefer a command line can use the basic setup script. This path requires
[Git](https://git-scm.com/) and [Node.js 20+](https://nodejs.org/):

```bash
git clone <repository-url>
cd secondbraintemplate
npm run setup
```

Both setup paths create three gitignored files:

- `USER.md` — confirmed identity and working preferences.
- `NOW.md` — current priorities and open loops.
- `projects/local-paths.md` — machine-specific paths to other repositories.

Running setup again will not overwrite those files unless you explicitly confirm it.

## What Lives Where

- `Dashboard.md` — command center and navigation.
- `USER.md` — private local profile created during setup.
- `NOW.md` — private local priorities created during setup.
- `projects/` — project registry and reusable profile template.
- `wiki/` — durable, sourced knowledge and decisions.
- `outputs/` — local reviewable reports.
- `runtime/` — local automation status.
- `AGENTS.md` — operating rules for AI assistants.
- `ONBOARDING.md` — required first-run interview and completion checklist.
- `BRANDING.md` — naming and matching-icon workflow.

## Privacy Before Syncing

The starter repository contains no personal profile or private source material.
`USER.md`, `NOW.md`, local paths, runtime state, and generated reports are ignored by
Git. The validator also rejects them if they are accidentally force-added.

The durable wiki and project profiles are tracked so they can be portable. Do not put
private information in those tracked files while the repository is public. If the
second brain will hold personal memory across devices, first make the GitHub
repository private, review the privacy rules in `CONFIGURATION.md`, and commit only
the material the owner intentionally wants to sync.

## Useful Commands

These commands are optional developer conveniences, not prerequisites for using
the template:

```bash
npm run setup      # create or refresh private local configuration
npm run validate   # check structure, links, privacy boundaries, and placeholders
npm test           # run the full validation suite
```

See `CONFIGURATION.md` for customization and migration guidance.
