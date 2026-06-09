# AGENTS.md

Policy for any coding agent or contributor working in this repository.

## §0 — Repository policy (hard rules)

- **Role-based identifiers only.** No personal names anywhere — repo files,
  configs, scripts, commit messages, or comments. Use role-based identifiers
  (e.g. `authorized_user_1`, `household_member_1`, `district_admin_1`).
- **No disallowed commit-message trailers.** Enforced by a local `commit-msg`
  policy hook; auto-trailer insertion is also disabled in operator settings.
- **No employer or third-party client references** in committed content.
- **DLP gate required.** A DLP pre-commit hook blocks internal IP ranges,
  hardware/vehicle nicknames, and personal-context terms. Do not bypass it;
  sanitize all public-facing artifacts before push.
- **Never read secret-bearing files.** `.env`, credstore contents, `*.key`,
  `*.pem`, and age/SSH identity files are off-limits to read/grep/cat/echo/print
  for any agent or tool — reference them by name and path only. A leaked secret
  value cannot be un-leaked by a hook; this rule is the prevention.
