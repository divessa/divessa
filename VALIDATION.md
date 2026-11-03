# Validation report — DIVERSA profile package

Date: 2026-11-02

## Verified using authoritative project documentation

- The two showcased repository URLs and their implementation claims were checked against their publicly accessible GitHub repository pages.
- `git-koi@v1.0.2` is a published release with the documented `login`, `body`, `output-dir`, and `token` inputs; `asagi` is supported. The output `koi/koi.gif` is documented.
- `seijikohara/profile-cards-action@v1.17.2` is a published release. The documented inputs cover `github-token`, `username`, `cards`, `output-dir`, `themes`, `palette`, and `commit`.
- `stats-organization/github-readme-stats-action@v2.1.0` is a published release. Its documented pin-card inputs include `card`, `options`, `path`, `token`, and `fail_on_error`.
- `yoshi389111/github-profile-3d-contrib@v0.9.3` is a published release. Its documented `GITHUB_TOKEN`/`USERNAME` environment variables and `profile-night-view.svg`/`profile-green-animate.svg` output paths were checked.
- `capsule-render` and `readme-typing-svg` support the selected hosted SVG URL-configuration model.

## Must be validated after upload

- Genuine account-specific koi rendering, GIF frame count, and visual appearance.
- GitHub Actions runtime execution, API permissions, and ability to push generated assets.
- Exact light/dark appearance of generated assets in GitHub's sanitizer and on mobile.
- Availability of the two hosted SVG services at page-load time.

The test summary printed during local package validation should not be mistaken for a successful live GitHub Actions run.

## Local validation executed

The isolated build environment parsed all three workflow YAML files using PyYAML, parsed `README.md` with a CommonMark renderer supporting embedded HTML, verified that all nine image elements have alt text, checked dark/light source selectors, checked workflow-generator release references and koi settings, and cross-checked every generated asset path against the workflows. Ten automated assertion groups passed.

**Not claimed:** a live GitHub Actions run, a rendered koi GIF, a desktop/mobile browser screenshot of the deployed profile, or availability of hosted remote SVGs at runtime. The container cannot reach GitHub's asset hosts or use this account's GitHub Actions.

## Pre-deployment design evaluation

| Criterion | Weight | Assessment |
|---|---:|---|
| Immediate visual impact | 25% | Strong layered header, typography, koi and 3D; visual rendering still needs live verification. |
| Repository prominence | 20% | Two verified codebases are the first major section, each with direct source and Issues links. |
| Contributor attraction | 20% | Direct contribution funnel, credible motivations and explicit protections against equity/compensation implications. |
| Futuristic sophistication | 15% | Five complementary existing visual systems, two of which are animated; no custom rendering engine. |
| Originality of composition | 10% | Original copy, strict repository-first hierarchy and constrained telemetry. |
| Reliability and maintainability | 10% | Release-pinned workflows and no manual PAT; reliance on two hosted SVGs and yet-unrun workflows is the main risk. |

**Main unresolved blocker:** the account-specific animated koi cannot be generated or runtime-tested inside this environment. Deployment will be complete only after its GitHub Actions workflow successfully generates `koi/koi.gif` and the file is observed animating on GitHub.
