# macOS

An opinionated guide to setting up an excellent Mac: fast, calm, secure, and
pleasant to use every day.

This is a work in progress. The goal is not to collect every possible tweak.
It is to document a coherent setup, explain why each choice earns its place,
and make the whole thing reproducible on a new Mac.

## What this guide will cover

- First-run macOS settings
- Security, privacy, backups, and recovery
- Window management and desktop behavior
- Keyboard, trackpad, and input improvements
- Essential applications
- Terminal and developer tooling
- Focus, notifications, and quality-of-life defaults
- Automation and repeatable setup
- Optional advanced configuration

## Principles

1. Prefer native macOS features when they do the job well.
2. Add software only when it solves a real problem.
3. Keep important settings understandable and reversible.
4. Protect security and privacy without making the computer miserable to use.
5. Automate repeatable setup, but document what the automation changes.
6. Separate universal recommendations from personal preferences.

## Guide

The detailed guide is being written. It will distinguish between:

- **Recommended** — sensible for almost everyone
- **Optional** — useful for a particular workflow or preference
- **Advanced** — powerful, but worth understanding before enabling

### Disable the Dock

If you launch apps with Spotlight or another keyboard-first launcher, the Dock
can become mostly wasted space. macOS does not offer an official “off” switch,
but you can hide it and make its reveal delay long enough that it is effectively
disabled. This preserves Mission Control, Spaces, and the other system features
managed by the Dock process.

First turn on **System Settings → Desktop & Dock → Automatically hide and show
the Dock**. Then run:

```bash
defaults write com.apple.dock autohide -bool true
defaults write com.apple.dock autohide-delay -float 1000
defaults write com.apple.dock no-bouncing -bool true
killall Dock
```

The `no-bouncing` setting stops app icons from bouncing in the hidden Dock when
an app launches or requests attention.

To restore the normal hidden-Dock behavior:

```bash
defaults delete com.apple.dock autohide-delay
defaults delete com.apple.dock no-bouncing
killall Dock
```

[Minimized Windows](https://github.com/numeono/minimized-windows) is especially
useful with this setup because minimized windows remain accessible without the
Dock.

## Related projects

- [Minimized Windows](https://github.com/numeono/minimized-windows) — a small
  menu-bar app for finding and restoring minimized windows.

## License

MIT. See [LICENSE](LICENSE).
