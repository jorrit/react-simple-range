# react-simple-range

[![npm version](https://img.shields.io/npm/v/react-simple-range.svg?style=flat)](https://www.npmjs.com/package/react-simple-range)
[![travis build](https://img.shields.io/travis/tjallen/react-simple-range.svg?style=flat)](https://travis-ci.org/tjallen/react-simple-range)
[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg)](http://commitizen.github.io/cz-cli/)

A simple React slider component for inputting a number value within a range.

![](http://thomjamesallen.com/images/reactsimplerange-post-crop.jpg)

## Examples

- For local examples check out the [Development](#development) section below
- [Or view examples online here](http://thomjamesallen.com/projects/react-simple-range-examples/)

## Install

```npm install react-simple-range --save```

## Usage

Import React and this component using your chosen module bundler:

```
import React from 'react';
import ReactDOM from 'react-dom';
import ReactSimpleRange from 'react-simple-range';
const rootElement = document.getElementById('app');

ReactDOM.render(<ReactSimpleRange />, rootElement);
```

## Props

Name | Type | Default | Description
---|---|---|---
min | number | 0 | Minimum slider value
max | number | 100 | Maximum slider value
step | number | 1  | Number inc/decremented when slider value is changed. The range of the slider (max - min) should be evenly divisible by this
id | string | `null` | Identifier that is passed to the onChange handler (see below)
onChange | function | [NOOP](https://en.wikipedia.org/wiki/NOP) | Function to be called when the slider value changes - your slider will have no effect without this! See below for more information
value | number | `props.defaultValue` | Set current value of slider
defaultValue | number | 0 | Set initial value of slider
vertical | boolean | `false` | Set slider to vertical when true
verticalSliderHeight | string | `100px` | Default slider height if vertical. If your slider already has a fixed height wrapper, just set this to `100%` and the slider will fill the space
eventWrapperPadding | number | 8 | Px value to add padding to the wrapper to make small sliders easier to interact with
label | boolean | `false` | If true, adds a label displaying the slider's value when interacted with
disableThumb | boolean | `false` | Disables the thumb when true
disableTrack | boolean | `false` | Disables the track when true
sliderSize | number | 4 | Px height of slider if horizontal, width if vertical
thumbSize | number | `sliderSize * 2` | Height and width of thumb in px
sliderColor | string | `#9E9E9E` | Color of slider
trackColor | string | `#03A9F4` | Color of track and label
thumbColor | string | `#fff` | Color of thumb
customThumb | element | `undefined` | Pass in a single React element to use as your thumb, replacing the default

## The onChange handler

The onChange handler receives one argument: the new state of the component.
It contains the following properties:

Name | Type | Description
---|---|---
value|number|Current value
min|number|Minimum value (from props)
max|number|Maximum value (from props)
range|number|Difference between `max` and `min`
step|number|Step value (from props)
ratio|number|Percentage of bar filled
thumbSize|number|Thumb size value (from props)

## Development

Clone the repo then run ```npm start``` in the cloned directory to start webpack-dev-server and serve the examples.

Note: The examples import the  [babel-polyfill](https://babeljs.io/docs/usage/polyfill/) for compatibility in development, but the component itself doesn't

### Contributing

PRs are welcome. This project uses [Commitizen](https://github.com/commitizen/) with the cz-conventional-changelog adapter - see the [Angular commit guidelines](https://github.com/angular/angular.js/blob/master/CONTRIBUTING.md#-git-commit-guidelines) for more info.

This means that, when working on your fork, instead of running `git commit` in your CLI, you should use `npm run cz` (after staging your changes as usual with `git add`).

Commitizen will then walk you through the process of creating a commit using the guidelines.

## Commands for local dev

Name | Effect
:---|:---
`npm start` | Starts a webpack-dev-server & serves the `examples/` directory to `http://localhost:8080/`
`npm run test` | Runs tests with `mocha`
`npm run test:watch` | Runs tests in watch mode with `mocha --watch`

## Future

- Better test coverage
- Submit an issue to add to this list
