# WordPress Quality Gates

Use the gates that match the task:

- **Scope:** target URL/repository, changed pages/files, and unrelated changes are known.
- **Safety:** backup and rollback path exist before database, media, plugin, theme, or migration changes.
- **Builder:** native Elementor widgets, Flexbox, global styles, consistent image ratios, hover/focus states, and no legacy layout unless required.
- **Responsive:** desktop, tablet, and a narrow mobile viewport have no horizontal overflow.
- **Content:** headings, buttons, links, image alt text, and placeholder contact details are intentional.
- **Runtime:** admin/editor loads, relevant pages return expected HTTP statuses, and no new console/PHP/Apache errors appear.
- **Code:** relevant lint, type, test, validator, or static-analysis checks pass.
- **Release:** secrets, database dumps, backups, and local environment files are excluded from version control.

Report any gate that could not be checked instead of implying it passed.
