# OpenCode Configuration

Personal [OpenCode](https://opencode.ai/) configuration with reusable skills, slash commands, and conservative permissions for Git and GitHub operations.

## Setup

Back up any existing OpenCode configuration, then clone this repository into OpenCode's default configuration directory:

```sh
mv ~/.config/opencode ~/.config/opencode.backup
git clone <repository-url> ~/.config/opencode
```

Restart OpenCode after cloning so it discovers the commands and skills.

## Commands

| Command | Purpose |
| --- | --- |
| `/commit` | Draft a conventional commit title from staged changes and commit after approval. |
| `/pr-create` | Analyze the current branch, draft a pull request, and create it with GitHub CLI. |
| `/prototype` | Build a throwaway logic or UI prototype to answer a design question. |
| `/grill-me` | Stress-test a plan, decision, or idea through structured questions. |
| `/teach` | Create a workspace-based learning path for a skill or concept. |

Commands are thin entry points in `commands/`. Their detailed workflows live in the corresponding `skills/` directories.

## Safety Defaults

`opencode.json` limits destructive or remote operations:

- Denies pushes, hard resets, forced branch deletion, repository deletion, pull-request merges, and secret management.
- Requires confirmation for rebases, amended commits, pull-request edits, issue closure, and release creation.
- Leaves routine local inspection and editing available to the agent.

Review these permissions before adapting the configuration to your own workflow.

## Repository Layout

```text
.
├── commands/       # Slash-command entry points
├── skills/         # Reusable agent workflows and supporting files
├── opencode.json   # OpenCode permissions and configuration
└── README.md
```

## Credits

The `prototype`, `grilling`, and `teach` skills are adapted from [Matt Pocock's skills repository](https://github.com/mattpocock/skills). See each skill's metadata and license for details.
