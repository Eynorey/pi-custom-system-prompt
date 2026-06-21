# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.1.0] - 2026-06-21

### Added

- Initial release.
- Load a custom system prompt from `~/.pi/agent/system-prompts/<file>.md` and inject it on every agent turn via the `before_agent_start` event.
- Commands: `/system-prompt-info`, `/system-prompt-toggle`, `/system-prompt-reload`, `/system-prompt-mode`, `/system-prompt-show`, `/system-prompt-select`.
- Two modes: `append` (default; keep Pi's prompt as the base and add the custom prompt as an extra section) and `replace` (use the custom prompt as the base, with Pi's tools and user customizations appended after it).
- Multiple `.md` files can coexist in the prompt directory; use `/system-prompt-select` to switch between them.
- Persistent state (`enabled`, `mode`, `selectedFile`) saved to `~/.pi/agent/state/system-prompt.json` and reloaded on next start.
- Footer status widget: `system-prompt: <file>` when enabled, `system-prompt: disabled` when not.
- `PI_SYSTEM_PROMPT_DIR` environment variable to override the default prompt directory.
