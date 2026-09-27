# Contributing

Thanks for your interest in improving **Java Development**! This is a learning
repository, so contributions range from fixing a typo to adding exercises to a
notebook or a new project.

## Ways to contribute

- 🐛 Report a factual or code error in an issue.
- 📝 Improve an explanation, add examples, or write a guide.
- 🧪 Add exercises and solutions to a notebook.
- 🎨 Fix repository hygiene (docs, CI, build files).

## Development setup

```bash
# 1. Clone
git clone git@github.com:Davin-X/java-development.git
cd java-development

# 2. Prerequisites (Java 17+, Python 3.10+ for notebook tooling)
java -version && javac -version

# 3. Compile the Java sources
find . -name "*.java" -print0 | xargs -0 javac -d /tmp/java-build

# 4. Start learning
jupyter lab
```

## Notebook conventions

- Notebooks are the curriculum: keep the **objectives → concepts →
  exercises → summary** shape where it exists.
- Commit notebooks with outputs **cleared** unless the change is specifically
  about rendered output.
- Keep notebooks machine-checkable with `nbformat` validation in CI.

## Java conventions

- Java 17 baseline; prefer records, sealed types, and pattern matching where
  they clarify the lesson.
- New `.java` files must compile with plain `javac` (no IDE-only setup).

## Commits

Conventional Commits, e.g. `docs(notebooks): add exercises to 02_control_structures`.

## Pull requests

1. Branch from `main` (e.g. `docs/fix-typos`).
2. Make focused changes with a clear commit message.
3. Update `README.md` / `CURRICULUM_GUIDE.md` when content changes.
4. Open a PR; CI compiles sources and validates notebooks.

## Code of Conduct

Be respectful — see [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md).
