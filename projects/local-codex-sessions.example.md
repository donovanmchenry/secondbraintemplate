# Local Codex Tasks

Copy this file to `projects/local-codex-sessions.md` only when a project needs a
private, machine-specific pointer back to a Codex task. The copied file is
gitignored.

```text
- project: [PROJECT ID]
  working directory: [ABSOLUTE LOCAL PATH]
  task ID: [PRIVATE TASK ID]
  task link: [PRIVATE LOCAL CODEX LINK]
  purpose: [WHAT CONTINUING THIS TASK SHOULD ACCOMPLISH]
  last checked: [YYYY-MM-DD]
```

Keep this file as routing data, not memory. The project profile remains the source for
stable non-sensitive context, and the project repository remains authoritative for
its code and current operational state. Never put task IDs, local paths, or private
task links in tracked project profiles.
