# Contributing to Auto Grove

Thanks for taking the time to help improve Auto Grove.

This repository hosts the **documentation and public issue tracker** for the mod. The mod's source code is closed and distributed exclusively through the official GIANTS ModHub. We are not accepting code pull requests.

There are still two productive ways to contribute:

## 1. File a bug report

If something doesn't work the way the documentation says it should, please open an issue using the [Bug Report template](../../issues/new?template=bug_report.yml).

Useful bugs include all of:

- Your Auto Grove version (visible in the in-game mod menu).
- Your Farming Simulator 25 version.
- Whether the bug happens in single-player, on a dedicated server, or both.
- The map you were playing, and the field number if it's field-specific.
- A short list of steps to reproduce the issue.
- The relevant lines from your `log.txt` (located at `Documents\My Games\FarmingSimulator2025\log.txt`).

Auto Grove logs every step of a planting job — the field clear, the placeable it resolved, the row layout, the pacing, and the final charge — all prefixed with `[AutoGrove]`. Those lines are by far the most useful thing you can attach, and they usually identify the problem on their own.

A vague "planting doesn't work" report is hard to act on — a 5-line repro plus the `[AutoGrove]` log lines typically gets a fix into the next ModHub submission.

### Before you file

Two behaviours are documented and expected rather than bugs:

- **AI helpers refuse to work in a vineyard.** This is a base-game limitation that applies to any vineyard, including hand-built ones. See the README.
- **Guidance lines run over the plants.** This depends on your implement, not on the grove. Vineyard harvesters straddle the row by design; between-row tools drive the alley. See the README.

## 2. Request a feature

Open an issue using the [Feature Request template](../../issues/new?template=feature_request.yml). Describe the use case before the implementation — *what* you want to do, *why* you currently can't, and *who* it would help.

Feature requests are evaluated against the project's design principles:

- **The result must be indistinguishable from a hand-built grove.** Auto Grove automates placement; it does not invent new farming mechanics or bypass the game's own rules.
- **The server is the authority.** Anything a client could assert about ownership, permissions, or money is re-checked server-side. Features that would require trusting the client are out of scope.
- **No console commands.** Everything belongs in the F6 panel where players can find it.
- **Vanilla pricing stays vanilla.** Ordering a grove should be neither a discount nor a penalty compared with building it by hand. Discounts are a server admin's decision, not a default.

## Code of conduct

Be respectful. Personal attacks, harassment, and off-topic disputes will result in the issue being locked. We are a small volunteer project; treating maintainers and other contributors well is the only price of admission.

## What we cannot accept

- **Pull requests adding or modifying code in this repository.** The mod source is closed. Documentation typo fixes are welcome via PR.
- **Reverse-engineered code** posted in issues or comments. Doing so is a violation of the mod's [LICENSE](LICENSE) and the issue will be deleted.
- **Support requests for other mods.** If a third-party mod is conflicting with Auto Grove, please include the details here, but raise the issue on that mod's tracker as well.
