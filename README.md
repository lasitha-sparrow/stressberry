# stressberry

Stress tests for the Raspberry Pi.

[![CircleCI](https://img.shields.io/circleci/project/github/nschloe/stressberry/master.svg)](https://circleci.com/gh/nschloe/stressberry/tree/master)
[![awesome](https://img.shields.io/badge/awesome-yes-brightgreen.svg)](https://img.shields.io/badge/awesome-yes-brightgreen.svg)
[![PyPi Version](https://img.shields.io/pypi/v/stressberry.svg)](https://pypi.python.org/pypi/stressberry)
[![GitHub stars](https://img.shields.io/github/stars/nschloe/stressberry.svg?style=social&label=Stars&maxAge=2592000)](https://github.com/nschloe/stressberry)

<img src="https://nschloe.github.io/stressberry/all.png" width="70%">

There are a million ways to cool down your Raspberry Pi: Small heat sinks,
specific cases, and some [extreme DIY solutions](https://youtu.be/WfQMLInuwws).
stressberry is a package for testing the core temperature under different
loads, and it produces nice plots which can easily be compared.

To run stressberry on your computer, simply install it with
```
[sudo -H] pip3 install -U stressberry
```
and run it with
```
stressberry-run out.dat
stressberry-plot out.dat [-o out.png]
```
The run lets the CPU idle for a bit, then stresses it with maximum load for 5
minutes, and lets it cool down afterwards. The entire process takes 10 minutes.
The resulting data is displayed to a screen or, if specified, written to a PNG
file.

If you'd like to submit your own data for display here, feel free to
[open an issue](https://github.com/nschloe/stressberry/issues) and include the
data file, a photograph of your setup, and perhaps some further information.

### The setups

#### A naked Raspberry Pi 3

<img src="https://nschloe.github.io/stressberry/naked-photo.jpg" width="30%">

The Raspberry Pi 3 without fans, heat sinks, or particular cases. The idle core
temperature is about 47°C, under heavy load it reaches 80°C (at which point the
CPU frequency is throttled).

#### A simple acryl case

<img src="https://nschloe.github.io/stressberry/acryl-photo.jpg" width="30%">

Your average acrylic case from eBay. Temperature measurements are bit warmer
than with the naked Raspberry Pi, presumable because the case hinders the free
air flow.

### Testing

To run the tests, just check out this repository and type
```
pytest
```

### Distribution

To create a new release

1. bump the `__version__` number,

2. publish to PyPi and GitHub:
    ```
    $ make publish
    ```

### License
stressberry is published under the [MIT license](https://en.wikipedia.org/wiki/MIT_License).
