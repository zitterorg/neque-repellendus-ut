# A11y Contrast

![npm](https://img.shields.io/npm/v/@zitterorg/neque-repellendus-ut?style=flat-square)
[![Build](https://img.shields.io/github/actions/workflow/status/darekkay/@zitterorg/neque-repellendus-ut/ci.yml?branch=master&style=flat-square)](https://github.com/zitterorg/neque-repellendus-ut/actions/workflows/ci.yml)
[![license](https://img.shields.io/badge/license-MIT-green?style=flat-square)](https://github.com/zitterorg/neque-repellendus-ut/blob/master/LICENSE)

A CLI utility to calculate/verify accessible [magic numbers](https://designsystem.digital.gov/design-tokens/color/overview/#magic-number) for a color palette. Read [my blog post](https://darekkay.com/blog/accessible-color-palette/) for some more information.

![](screenshot.png)

## Installation

This tool requires Node.js version 18+.

Install globally:

```bash
$ npm install -g @zitterorg/neque-repellendus-ut  # Npm
$ yarn add -g @zitterorg/neque-repellendus-ut     # Yarn
```

Or install as a local dependency:

```bash
$ npm install --save @zitterorg/neque-repellendus-ut  # Npm
$ yarn add @zitterorg/neque-repellendus-ut            # Yarn
```

Or use without installing:

```bash
$ npx @zitterorg/neque-repellendus-ut <file>
```

## Usage

View program help:

```
$ @zitterorg/neque-repellendus-ut --help
Usage: @zitterorg/neque-repellendus-ut <file> [options]

Arguments:
  <file>  Color palette file                              [required] [file]

Options:
  --min-ratio-3    Verify magic number for ratio 3                 [number]
  --min-ratio-4.5  Verify magic number for ratio 4.5               [number]
  --min-ratio-7    Verify magic number for ratio 7                 [number]
  -h, --help       Show help                     [commands: help] [boolean]
  -v, --version    Show version number        [commands: version] [boolean]
```

Run a full report for a color palette file:

```bash
$ @zitterorg/neque-repellendus-ut <file>
```

Verify that the color palette fulfills certain magic numbers per contrast ratio:

```bash
$ @zitterorg/neque-repellendus-ut <file> --min-ratio-3=40 --min-ratio-4.5=50 --min-ratio-7=70
```

## Color palette format

This tool handles flat or nested JSON files. Any consistent grading system is supported.

- Flat JSON:

```json
{
  "blue-10": "#d9e8f6",
  "blue-20": "#aacdec",
  "blue-30": "#73b3e7",
  "green-10": "#dfeacd",
  "green-20": "#b8d293",
  "green-30": "#9bb672"
}
```

- Nested JSON:

```json
{
  "blue": {
    "blue-100": "#d9e8f6",
    "blue-200": "#aacdec",
    "blue-300": "#73b3e7"
  },
  "green": {
    "green-100": "#dfeacd",
    "green-200": "#b8d293",
    "green-300": "#9bb672"
  }
}
```

Check out some example color palettes under `/examples`.

## License

This project and its contents are open source under the [MIT license](LICENSE).
