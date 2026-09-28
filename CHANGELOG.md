# Release notes

<!-- do not remove -->

## 0.4.0

### Breaking Changes

- Replace lisette with fastllm; mapping and section extraction are now async ([#1](https://github.com/franckalbinet/iomeval/issues/1))

### New Features

- Document the curator app in the README ([#6](https://github.com/franckalbinet/iomeval/issues/6))

### Bugs Squashed

- CI and docs deploy fail on research notebooks and undeclared llm_eval dependencies ([#8](https://github.com/franckalbinet/iomeval/issues/8))
- python -m iomeval.curator fails to serve the app ([#7](https://github.com/franckalbinet/iomeval/issues/7))
- README Quick Start uses an outdated run_pipeline call ([#5](https://github.com/franckalbinet/iomeval/issues/5))
- CCP mapping example formats CCPs with fmt_enbs ([#4](https://github.com/franckalbinet/iomeval/issues/4))
- Report class is exported twice in pipeline.py ([#3](https://github.com/franckalbinet/iomeval/issues/3))
- iomeval fails to import with current toolslm ([#2](https://github.com/franckalbinet/iomeval/issues/2))
