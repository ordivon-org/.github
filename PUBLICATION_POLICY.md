# Ordivon Public-First Publication Policy

## Default

Ordivon is **public by default and private by explicit exception**.

Public Git is the normal carrier for source code, tests, reproducible research, design records, benchmark material, public evidence, and documentation when the material can be published lawfully and without disclosing sensitive reality.

Repository visibility does not decide copyright ownership, licence scope, patent rights, trademark rights, or authority to operate external systems. Those are separate standings.

## Publication classes

Every material publication decision should fit one of four classes:

1. `PUBLIC_NATIVE` — safe and rights-cleared in its authored form.
2. `PUBLIC_AFTER_SANITIZATION` — publish only through a verified privacy/security projection.
3. `EMBARGOED` — temporarily private while a patent, paper embargo, responsible disclosure, or equivalent time-bounded decision is unresolved.
4. `PRIVATE_INTRINSIC` — secrets, raw/linkable personal records, private correspondence, restricted third-party material, sensitive operational control state, and other material whose useful function depends on remaining private.

Private is therefore a reasoned state, not the default status of an unfinished repository.

## Material that must not be published directly

Public carriers must not contain:

- live credentials, tokens, cookies, private keys, signing material, recovery codes, or secret-bearing environment files;
- raw or linkable personal health, financial, relationship, behavioural, location, biometric, genetic, conversational, education, employment, legal, identity, or account records;
- private correspondence or internal discussions whose participants did not authorize publication;
- third-party proprietary, NDA-bound, access-restricted, or otherwise non-redistributable material;
- unpatched vulnerability details being handled through responsible disclosure;
- operational topology, endpoint identity, host/user naming, or other infrastructure detail when disclosure creates unnecessary risk;
- an invention intentionally held for a pre-filing patent decision.

## Sanitized publication

Sanitization should be deterministic where practical and must preserve semantic meaning. Prefer:

- synthetic fixtures over lightly transformed real records;
- aggregate or privacy-reduced evidence over raw individual data;
- opaque non-secret references over credentials or account identifiers;
- generalized host/path/network labels over unnecessary workstation identity;
- exact public source citations over copied restricted source material;
- metadata-only security Sample identity when Sample bytes belong in a private vault.

A sanitization step may remove or generalize sensitive fields, but it must not silently turn an unknown, failed, provisional, or private observation into a stronger public claim.

## Git history and refs are part of publication

Changing a repository from private to public publishes more than the current working tree. Branches, tags, reachable commit history, commit metadata, and historical blobs must be considered part of the publication boundary.

Before visibility promotion:

1. scan the complete remote Git history for secrets;
2. inspect current and branch-only content for personal/restricted/operational material;
3. confirm the repository licence and third-party notices;
4. confirm there is no unresolved patent or responsible-disclosure embargo;
5. record the repository's publication standing.

If a real secret existed in reachable history, rotate/revoke it first and rewrite the affected public history when necessary. An allowlist is appropriate only for proven non-secret fixtures or false positives.

## Security research

Security source, methods, simulations, metadata, and owned-range evidence may be public. Live third-party exploitation, undeclared external effects, private Sample bytes, credentials, and responsible-disclosure material may not.

## Patent-sensitive work

Potentially patent-relevant material may enter `EMBARGOED` standing long enough to decide whether to file before publication. Absence of a patent strategy is not itself a reason to keep ordinary engineering private.

## Rights

The repository `LICENSE` controls licence grants for the Work. Ordivon's default software licence is Apache-2.0. Contributor provenance uses DCO unless a repository explicitly states a different accepted mechanism. Trademark/branding rights remain separate from source licensing.

## Machine-readable standing

Repositories may provide `.ordivon/rights.yaml` and `.ordivon/publication.yaml`. Repository-local files may make this policy stricter for a specific domain but should not weaken secret, personal-data, third-party-rights, or responsible-disclosure boundaries.
