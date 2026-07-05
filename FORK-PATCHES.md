# Fork patches

This is max-winderbaum's fork of [samleeney/tmux-agent-status](https://github.com/samleeney/tmux-agent-status), carrying fixes we hit in daily use. Each patch is a standalone commit on top of upstream main, kept PR-ready.

| Commit | Fix |
|---|---|
| focus main pane after session select | Enter on a session row left focus on the sidebar pane |
| readable selection highlight on light themes | selected rows were invisible (dark bg + default dark fg) on light terminals |

## Known upstream bugs not yet patched here

- Spinner animation paints braille frames at stale absolute coordinates when the session list changes between renders (artifacts in the top-left / right edge).
- Switcher Ctrl-X silently fails on session rows that contain no agent.
- macOS `pgrep -a` prints bare PIDs (no command line), so agents display as generic "agent" instead of claude/codex.
- `prefix N` with an empty inbox leaves focus in the sidebar instead of no-oping visibly.

## Update workflow

    git fetch upstream && git rebase upstream/main && git push -f origin main
