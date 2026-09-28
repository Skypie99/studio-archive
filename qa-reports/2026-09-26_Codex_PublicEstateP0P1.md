> **Record note (added 2026-09-28 by the public-estate closure).** Preserved verbatim from the draft branch `codex/public-estate-p0p1-20260926` (PR #1) as a dated working record. Resolved since it was written: the custom domain `archive.skypistudio.com` was re-attached on 2026-09-27 with a valid Let's Encrypt certificate, HTTPS enforced and HTTP→HTTPS redirect (so the TLS failure and the GitHub Pages fallback described below no longer apply), the entry README landed via PR #2, and the About homepage points at the custom domain. Still owner-gated: code and creative-content reuse rights.

# Studio Archive public-estate P0/P1 remediation — 2026-09-26

## DECISIONS FOR SKY

- [ ] **Review and adopt the entry README.** Recommend this documentation-only branch to explain the public edition and give visitors a working preview link. The alternative is to defer it, leaving the missing repository entry explanation. Sky controls merging; no deployment is performed here.
- [ ] **Resolve the custom archive domain and canonical URL.** Recommend retaining the verified GitHub Pages fallback until Sky corrects TLS/DNS/hosting and decides the canonical public URL. The alternative is retiring the custom domain and separately reconciling metadata. The advertised custom-domain certificate still fails hostname validation; README correction does not repair hosting, search metadata, repository description, or links elsewhere.
- [ ] **Choose code and creative-content reuse rights.** Recommend separate explicit owner terms after deciding intended reuse. The alternative is retaining public viewing without a supplied reuse license. This patch grants no rights and adds no license.

## Branch and changed files

Base: `831c0aa53574aa539d06caac5adeae0bca966c0e`, verified public main.
Branch: `codex/public-estate-p0p1-20260926`.
README implementation commit: `afa697bdb1defc0acd99e957bc69b2b7cb5227f4`.

Added README.md: public palette/catalog purpose, separation from Portfolio’s private archive, dated source observation, GitHub Pages fallback, local static inspection command, and owner-only rights/domain decisions.
Added qa-reports/2026-09-26_Codex_PublicEstateP0P1.md: this receipt.
No existing source, catalog, artwork, assets, sitemap, robots, or runtime behavior changed. SA-02 is addressed on this branch. SA-01 remains partially addressed through a safe navigation fallback, with the domain repair held for Sky. No P0 finding was established by the controlling audit for this repository.

The old known checkout had a broken Git pointer to an absent primary repository. No valid alternative checkout was located; AGENTS.md and CLAUDE.md were absent at the old locations and in public source. The managed worktree tool was unavailable from the projectless chat (not a Git repository), so a fresh isolated bare repository and Codex worktree were created from the verified public head. The broken old checkout was preserved. No process cwd under the known archive/estate path was observed; unseen writers remain unverified.

## Gates and actual results

```bash
git diff --cached --check
```

Exit 0, no output before the README commit. A local Markdown check verified balanced code fences and the index.html link; zero missing local links.

A local Python static server was bound to loopback, fetched once, and stopped. Result: HTTP 200 and response bytes equal current index.html. This validates static inspection, not accessibility acceptance.

Prettier 3.8.3 was invoked from an existing dependency tree by an absolute path withheld from this public receipt. Portable equivalent arguments:

```bash
node node_modules/prettier/bin/prettier.cjs --check README.md
```

Exit 0: `Checking formatting...`; `All matched files use Prettier code style!`. No dependencies were installed for this static repository.

```bash
curl --silent --show-error --max-time 20 --output /dev/null --write-out '%{http_code}\n' https://archive.skypistudio.com
```

Exit 60, HTTP 000: `SSL: no alternative certificate subject name matches target host name`. Certificate verification was not disabled.

```bash
curl --silent --show-error --max-time 20 --output /dev/null --write-out '%{http_code}\n' https://skypie99.github.io/studio-archive/
```

Exit 0, HTTP 200.

Exact byte comparison confirmed index.html unchanged from the base. README contains no personal phone/account/credential fields, machine-specific paths, unsupported first-publication date, or invented license. New file allowlist: README.md and this QA receipt. Independent candidate review and remote PR identity are recorded in the final owner handoff.

## Remaining work and scope

Custom-domain/metadata rights decisions remain owner actions. The audit’s zoom/modal accessibility defects are P2, outside this documentation-only session; no fresh browser accessibility certification is claimed. Repository default is unchanged and has no README until owner adoption. No product build or test suite exists in this six-file static repository; none was invented or run.

Rollback: close or leave the draft before merge, or use an inverse documentation commit after owner adoption. No history rewrite is required to undo these new documents.

## Process self-check

Efficiency: reconciled the existing draft artifacts and public source; avoided unsupported provenance/artwork-photo claims in those drafts. Overlap: preserved the broken checkout and all prior drafts. Simplification: supplied a README and working fallback without modifying viewer, hosting, metadata, or rights.

Main direct writes, merges, deploys, history rewrites, and credential rotations: NONE.
