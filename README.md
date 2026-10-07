# Slither fork — gas-efficiency research notes

Fork of [Trail of Bits’ Slither](https://github.com/crytic/slither), a Python Solidity static-analysis framework. The existing source and [AGPL-3.0 license](LICENSE) retain their upstream attribution.

## Personal changes observed

The 7 October 2026 upstream comparison found one additional commit, [`58e97f8`](https://github.com/demis1997/slither/commit/58e97f8748d679006d2cc38d5ff149372ccc08a5), changing the README only. It records an intention to investigate gas-efficiency detectors. No new implemented detector is established by that diff. The default branch is 2,306 commits behind the inspected upstream; updating it requires a separate reviewed decision.

## Historical code setup

`setup.py` declares Python >=3.8 and the `slither` console entrypoint. An isolated installation would be:

```sh
python3 -m venv .venv
.venv/bin/python -m pip install -e .
.venv/bin/slither --help
```

These commands were inspected, not executed. Dependency/compiler compatibility and analyses are unverified. For current upstream behavior, consult the upstream project documentation. This fork is educational research, not a production security-audit result.

## Original planning notes

# Slither, the Solidity source analyzer
Trying to implement a gas efficiency analyzer into slither by altering documentation within slither repo to provide workaround based on https://betterprogramming.pub/solidity-gas-optimizations-and-tricks-2bcee0f9f1f2.
Creating another folder named gas inefficiencies with informational level (green) detectors for different gas inefficiencies.
