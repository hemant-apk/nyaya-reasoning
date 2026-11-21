# Contributing

Thanks for helping improve this skill. The repository is maintained by [K Hemant Kumar](https://github.com/hemant-apk). The most useful contribution is evidence about where it works and where it doesn't.

## Ways to help

- **Report test results.** Open an issue at https://github.com/hemant-apk/nyaya-reasoning/issues with the question, the plain answer, the skill answer, and which you judged better and why. Failures are especially valuable.
- **Report problems.** Cases where the skill made an answer longer, more pessimistic, or more formal than needed.
- **Propose changes.** Open an issue first for anything larger than a wording fix.
- **Test on other platforms.** Say which platform and model you used, and whether you used the full or short prompt.

## Making a change

1. Fork the repository and create a branch.
2. Edit the files. Keep `skills/nyaya-reasoning/SKILL.md` under about 500 lines, and put long material in `references/`.
3. Keep `portable/full-prompt.md` and `portable/short-prompt.txt` in step with `SKILL.md`. They should say the same things in plain words.
4. Keep `portable/short-prompt.txt` under 1,500 characters. Check with `wc -c portable/short-prompt.txt`.
5. Add an entry under "Unreleased" in `CHANGELOG.md`.
6. Open a pull request that says what changed and shows at least one before-and-after example.

## Style

- Plain words. The Sanskrit terms are labels for the AI's own use and should stay out of answers unless the user uses them.
- Explain why a rule exists, not only what it is.
- Claims about performance need evidence. Do not claim the skill beats other methods unless a test shows it.
