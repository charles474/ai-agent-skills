---
name: npm-audit
description: Follow the project's NPM audit resolution workflow to identify and fix vulnerabilities in project dependencies.
license: MIT
compatibility: opencode
---

## NPM audit resolution workflow

This skill implements the project's NPM audit resolution workflow.

---

## When to use

Use this workflow when:

- Fixing vulnerabilities in project dependencies

This project prefers to use the `npm audit` command to identify and fix vulnerabilities in project dependencies. This workflow is designed to be followed when running `npm audit` and addressing any vulnerabilities that are found.

---

## Steps

1. Run `npm audit` to identify vulnerabilities in project dependencies.
2. Review the audit report to understand the vulnerabilities and their severity.
3. Prioritize the vulnerabilities based on their severity and potential impact on the project.
4. For each vulnerability, determine if it can be fixed by updating the affected package or if it requires a more complex resolution (e.g., waiting for a patch, finding an alternative package, etc.).
5. To fix most vulnerabilities using npm audit, run `npm audit fix` to automatically apply available fixes for vulnerabilities. This command will attempt to update packages to secure versions while respecting the version constraints defined in the project's `package.json` file.
6. If `npm audit fix` then fails, look to resolving vulnerabilities by updating the package, run `npm update <package-name>` to update the package to a secure version.
7. If a vulnerability cannot be fixed by updating the package, document the issue and any potential workarounds or mitigations in the project's issue tracker or documentation.
8. After addressing all vulnerabilities, run `npm audit` again to ensure that all vulnerabilities have been resolved or appropriately documented.
9. If any vulnerabilities remain unresolved, continue to monitor for updates to the affected packages and apply fixes as they become available.
10. Regularly repeat this process to maintain the security of project dependencies over time.
11. Do review the `security-audit.md` log (if available within a project) for any vulnerabilities that can be fixed by updating the package, and update the log accordingly.

---

## Documenting vulnerabilities

Vulnerabilities that cannot be fixed by updating the package should be documented in the `security-audit.md` log, along with any relevant information about the vulnerability and potential workarounds or mitigations.

Update the table for production and development dependencies in the `security-audit.md` log to reflect the current state of vulnerabilities and their resolutions.

---

## Managing overrides

1. If a vulnerability cannot be fixed by updating the package, and there is a known workaround or mitigation, consider using npm's `overrides` feature to temporarily resolve the issue while waiting for an official fix. This can be done by adding an `overrides` section to the project's `package.json` file, specifying the affected package and the version to use as a workaround.
2. Document any overrides used in the `security-audit.md` log, including the reason for the override and any relevant information about the vulnerability and the workaround.
3. Regularly review and update overrides as new information becomes available or as official fixes are released for the vulnerabilities.