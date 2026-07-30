# Changelog

## 1.1.0 — 2026-07-30

Contrast-audit release. An adversarial audit showed the old build gate only
checked 11 colors per variant against a single background. The gate now
verifies **all 222 shipped foreground/background pairs** per build, and the
palette was retuned until every pair passes:

- Comments and line numbers now meet WCAG AA (≥4.5:1) in all four variants —
  line numbers previously bottomed out at 1.8:1
- Text stays ≥3:1 when selected; selection backgrounds retuned in
  Night / Storm / Mist
- Debugging status bar gets an explicit readable foreground
- Inactive tab titles and input placeholders promoted to the brighter muted tone
- Night's bright-black ANSI lifted to ≥3:1
- Zed port gains terminal ANSI colors and selection/cursor (`players`) —
  Zed's built-in terminal now matches the rest of your tools
- Warp Dawn correctly declares `details: lighter`
- Minimum VS Code raised to 1.83 (indent-guide color keys)

## 1.0.1 — 2026-07-28

- Point repository links at the published GitHub repo

## 1.0.0 — 2026-07-28

Initial release.

- **Dancheong Night** — the flagship dark theme
- **Dancheong Dawn** — light theme on warm hanji-paper tones
- **Dancheong Storm** — high-contrast dark (7.5:1+ accents, 14.5:1 body text)
- **Dancheong Mist** — muted, desaturated dark for long sessions
- Every foreground/background pair passes WCAG contrast gates,
  enforced by the build pipeline — not checked by eye
- Bonus: iTerm2 and Alacritty ports in `extras/`
