# Contributing

Thanks for your interest in improving WATTs! To keep the single‑file app reliable and easy to deploy, please follow these guidelines.

## Ground Rules

1. **Do not break the single‑file contract.** Keep HTML/CSS/JS bundled unless there is a compelling reason to split (discuss first).
2. **Preserve functionality when adding comments.** Documentation edits must not alter behavior.
3. **Accessibility first.** Use device‑agnostic language. Maintain ARIA labels and keyboard paths. Ensure mobile readability.
4. **No external data sources.** Do not introduce network calls or trackers. The app must run fully client‑side.
5. **Respect content licensing.** Code is MIT; content/assets are restricted (see `legal/ASSETS_LICENSE.md`).

## Branch & PR Flow

- Create feature branches from `main`: `feature/<brief-name>` or `fix/<brief-name>`.
- Keep PRs small and focused. Include a summary of changes and screenshots/GIFs if UI is affected.
- Link to the relevant item in `docs/WATTs_Changelog.md` and update it as part of the PR.

## Style

- Use clear, consistent section markers:
  - HTML: `<!-- SECTION: ... -->`
  - JS: `/* REGION: ... */`
- Prefer semantic HTML and minimal inline styles. Keep existing class names for consistent styling.

## Testing Checklist (PRs)

- [ ] Pathway select works; overview modal opens/closes via keyboard and click
- [ ] Section flow: Intro → Sections 1–3 → Results → Print/Summary
- [ ] Explorer Mode (if affected): survey renders, top matches compute, deep‑dive works
- [ ] Mobile: labels wrap; tables do not overflow; buttons are reachable
- [ ] Print: summary includes optional responses when enabled

## Security

- No runtime network access. The only outbound actions are user‑initiated: print and `mailto:` links.
