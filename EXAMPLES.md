# Examples

## 1. Fake completion

### Bad
> Fixed the issue.

No build. No test. No runtime proof.

### Good
> Changed `src/api/client.ts`.
> `npm run build` passes.
> Runtime behavior is not yet verified in production.
> Status: LIKELY FIXED.

---

## 2. Scope drift

### Bad
Fixes one bug, then also:
- renames helpers
- reformats unrelated files
- removes old code
- tweaks neighboring components

### Good
Changes only the real target file.
Mentions unrelated issues without touching them.

---

## 3. Fake browser proof

### Bad
Uses `curl` and says:
> Browser flow works.

### Good
> Route returns 200.
> Browser interaction is still not verified.
> Status: CHANGED ONLY.

---

## 4. Phase violation

### Bad
User asked for diagnosis only.
Agent also implemented, deployed, and reported done.

### Good
> Root cause identified.
> Exact next fix prepared.
> Waiting for explicit go-ahead.

---

## 5. Wrong target artifact

### Bad
Agent edits a copied file, temp file, or backup, then claims success.

### Good
Agent confirms the real target artifact changed.

---

## 6. Honest blocker reporting

### Bad
> Almost done, probably a provider glitch.

### Good
> FAILED:
> - exact check: production wallet-assets API
> - exact route: `/api/wallet/assets`
> - exact error: `tonapi_429`
> - next exact fix: reduce request fanout or add retry/backoff
