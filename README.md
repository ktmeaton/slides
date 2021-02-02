# Slides

## Installation

Create a conda environment with dependencies.

```bash
conda env create -f environment.yaml
conda activate slides-env
pre-commit install
```

Install reveal.js as a submodule.

```bash
git submodule add https://github.com/hakimel/reveal.js.git
cd reveal.js && git checkout tags/4.1.0 && npm install && cd ..
```

## Slide Decks

1. [NCBImeta](https://ktmeaton.github.io/slides/ncbimeta/ncbimeta_2019-09-16.pdf)
2. [BEAP](https://ktmeaton.github.io/slides/beap2020/beap_2020-01-30.pdf)
