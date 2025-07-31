# Cloudsmith Assessment – Issue Report and Fix Summary

This document outlines the issues identified and resolved across key files involved in the Cloudsmith Python Package workflows.

---

## `pyproject.toml`

**Issues Found:**

- `name` and `version` were missing in the `[project]` block.
- Author block contained placeholder data.

---

## `build_package.yml`

**Issues Found:**

- Missing build command for the Python package.
- `dist` directory was not cleaned before the build.

---

## `release_package.yml`

**Issues Found:**

- No OIDC authentication enabled (`id-token: write` was missing).
- No Cloudsmith CLI setup for secure upload.

---

## `promote_package.yml`

**Issues Found:**

- Incorrect repository targets: `production` and `staging` were swapped.
- Static inputs: Required user-supplied `PACKAGE_NAME` and `PACKAGE_VERSION`.
- Missing tag logic: Did not use `ready-for-production` tag to filter packages.

---