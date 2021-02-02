# Slides

## Installation

### NodeJS

```bash
conda env create -f environment.yaml
conda activate slides-env
```

### Reveal.js

```bash
git submodule add https://github.com/hakimel/reveal.js.git
cd reveal.js && git checkout tags/4.1.0 && npm install && cd ..
```

### Reveal Plugins

Add reveal.js-menu repo copy to reveal.js plugins as ```menu```.

### Jekyll

```bash
bundle install
bundle exec jekyll build --verbose
bundle exec jekyll serve
```


## Slide Decks

### 2021-02-05 BEAP

* [HTML](https://ktmeaton.github.io/slides/2021/02/05_BEAP.html)
* [PDF](https://ktmeaton.github.io/slides/2021/02/05_BEAP.html?print-pdf)

1. [2021-02-05 BEAP](https://ktmeaton.github.io/slides/2021/02/05_BEAP.html#/title-slide)
1. [NCBImeta](https://ktmeaton.github.io/slides/ncbimeta/ncbimeta_2019-09-16.pdf)
1. [BEAP](https://ktmeaton.github.io/slides/beap2020/beap_2020-01-30.pdf)

## Reminders

- In reveal.js, press "s" for speaker view, timer, notes.
- In reveal.js, press "b" or "." to black out the screen to pause.