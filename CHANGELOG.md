# Changelog

## 1.2.0 — 2026-07-31

Coverage release. 1.1.0 made the colors honest; this one makes them reach the
rest of the editor.

- **Semantic highlighting**, which the theme previously did not support at all.
  37 semantic rules mean a language server's answer wins over a regex guess:
  a readonly binding is coloured as a constant, a parameter is distinguished
  from a local, `Foo` in type position differs from `Foo` in value position,
  and deprecated symbols are struck through rather than dimmed — a strikethrough
  costs no contrast, a dimmer colour does.
- **Workbench coverage 67 → 417 keys.** Bracket-pair colours, inlay hints,
  ghost text (inline suggestions), sticky scroll, peek view, the suggest and
  hover widgets, minimap and overview ruler, notebooks, testing, the merge
  editor, debug icons, symbol icons, the command centre, and the settings and
  welcome pages are all themed now. Anything left unset falls back to VS Code's
  defaults, which is how a theme ends up with colours it never chose.
- **The contrast gate grew with it, and got honest about its own count.**
  It now reports *distinct* pairs — 177 across the four variants. Counting
  checks rather than pairs had been inflating the figure, because the palette
  reuses colours across roles (the error colour **is** the red accent, the
  cursor **is** the yellow). Where one pair carried two thresholds, the
  stricter one wins. New coverage: text
  *on* coloured surfaces (buttons, badges, the error and warning status bar),
  syntax colours inside the suggest and hover widgets, and inactive UI states.
- Inlay hints ship with a transparent background on purpose. A tinted backdrop
  dropped them to 3.1–3.5:1; on the editor background they read at 4.6:1.

## 1.1.0 — 2026-07-30

Contrast-audit release. An adversarial audit showed the old build gate only
checked 11 colors per variant against a single background. The gate now
verifies **every shipped foreground/background pair** per build — 222 checks at
the time, though 1.2.0 later found that figure was counting the same pair more
than once; see that entry. The palette was retuned until every pair passes:

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
