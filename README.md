# Slides

## Content

- 2021-03-06 Workshop ([Notes](https://github.com/ktmeaton/slides/blob/master/2021/03/06_Workshop.md), [Plague Krona](https://raw.githack.com/ktmeaton/slides/master/2021/03/06_Workshop_Plague-Krona.html))
- 2021-02-05 BEAP ([HTML](https://ktmeaton.github.io/slides/2021/02/05_BEAP.html), [PDF](https://ktmeaton.github.io/slides/2021/02/05_BEAP.html?print-pdf))
- 2020-01-30 BEAP ([PDF](https://ktmeaton.github.io/slides/beap2020/beap_2020-01-30.pdf))
- 2019-09-16 NCBImeta ([PDF](https://ktmeaton.github.io/slides/ncbimeta/ncbimeta_2019-09-16.pdf))

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

```bash
mkdir plugins
cd plugins

git submodule add https://github.com/denehyg/reveal.js-menu.git menu

cd ..
```

### Jekyll

```basu
bundle install
bundle exec jekyll build --verbose
bundle exec jekyll serve
```

## Reminders

- In reveal.js, press "s" for speaker view, timer, notes.
- In reveal.js, press "b" or "." to black out the screen to pause.
