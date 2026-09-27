# Changelog

All notable changes to this project are documented in this file.
The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- `LICENSE` (MIT), `docs/CONTRIBUTING.md`, `docs/CODE_OF_CONDUCT.md`,
  `docs/SECURITY.md`.
- Honest CI: plain-`javac` compile of all sources (beginner and examples
  groups compiled separately — both define `Calculator` by design) plus
  `nbformat` notebook validation.
- `Java_Essentials.md` migrated from `tech-notes` into
  `0_Getting_Started/documentation/`.

### Changed
- `README.md` identity fixed: `Davin-X/java-development` clone URL and tree
  root; Spring Boot badge dropped (no Spring code in repo).
- `examples/Calculator_Application/README.md` no longer claims a Gradle
  wrapper; documents system Gradle and links the beginner `SimpleCalculator`.
- `1_Beginner/projects/README.md` links the two implemented projects.
- `.gitignore` rewritten: same coverage in ~40 lines, zero duplicates.

### Fixed
- Two notebooks (`06_Exception_Handling_Basics`, `07_IO_Operations`) were
  missing the required `kernelspec.name` field — patched, all 22 validate.
- CI compiles the two same-named programs separately so the build is green.
