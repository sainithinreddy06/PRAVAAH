# Testing and Verification Evidence

## What to verify

Use the repository's current workflow configuration and dependency files as the source of truth. A green CI run only validates the checks executed by that workflow; it does not automatically prove every feature works end to end in production.

## Recorded GitHub Actions evidence

The project README records these successful workflow runs for the development branch on 31 October 2026:

- [Frontend CI](https://github.com/sainithinreddy06/PRAVAAH/actions/runs/41222661389)
- [Backend CI](https://github.com/sainithinreddy06/PRAVAAH/actions/runs/41222661453)
- [Earlier backend CI run](https://github.com/sainithinreddy06/PRAVAAH/actions/runs/41221432068)

Check each run directly for its commit, workflow steps, and final status before citing it in a presentation or evaluation.

## Feature-specific verification

- **Audit chain:** Verify that the endpoint reports the result from the current environment. Relevant tests should cover a valid chain, altered event content, and authorization.
- **Evidence integrity:** Test successful download of unchanged bytes, rejection after file modification, and access-control boundaries.
- **Workflow authorization:** Test role and regional access restrictions as well as allowed and rejected state transitions.
- **Obligations and notifications:** Test status changes, overdue escalation, notification idempotency, and retry/failure behavior for supported channels.
- **Migrations:** Apply migrations against the supported relational database in a clean test environment.

## Reproducible local checks

Run commands from the directory and virtual environment appropriate to the checked-out branch. Typical checks, when configured, include:

```bash
npm ci
npm run build
```

For the backend, activate its virtual environment, install the repository's declared requirements, configure a test database, apply migrations, and run:

```bash
alembic upgrade head
python -m pytest
```

Use actual scripts and module paths from the checked-out branch; do not assume these examples fit every setup.

## Reporting results responsibly

Record the branch, commit SHA, environment, date, commands, and outcome. Distinguish automated tests, live demonstrations, and planned validation. Do not present synthetic audit events as institutional records or report unmeasured time savings, accuracy, or compliance improvements.
