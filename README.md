# toio.js

Library for controlling toio&trade;Core Cube using Node.js

- [API reference document](https://toio.github.io/toio.js/)
- [toio&trade;Core Cube technical specification](https://toio.github.io/toio-spec/)

## :computer: Prerequisites

- **Node.js** >= 8
- This library depends on [noble](https://github.com/noble/noble), so follow [noble's prerequisites](https://github.com/noble/noble#prerequisites) please.
  - Windows : needs Bluetooth 4.0 USB adapter. This video is good for beginners - [Bluetooth LE with Node.js and Noble on Windows](https://www.youtube.com/watch?v=mL9B8wuEdms&feature=youtu.be&t=1m46s)

## :white_check_mark: Verified Environment

#### Windows (10)

On Windows, we need additional settings (C++, python and special driver for BLE adapter). Please see noble's setup guide mentioned above.

#### macOS (10.12, 10.13 and 10.14)

We recommend 10.13 (High Sierra) and 10.14 (Mojave). On 10.12 (Sierra), the frequency of BLE notify event is slower than 10.13, 10.14 or Windows. This affects position correction logic (like used in chase sample).

#### Linux (not verified yet)

Not verified yet, we are waiting for your report.

## :package: Packages

| Package name  | Readme                                       | Description          |
| ------------- | -------------------------------------------- | -------------------- |
| @toio/scanner | [packages/scanner](./packages/scanner)       | Cube scanner         |
| @toio/cube    | [packages/cube](./packages/device-core-cube) | Cube BLE API wrapper |

## :video_game: Example

### How to play sample application

```sh
git clone https://github.com/toio/toio.js.git   # clone repository
cd toio.js                                      # move to repository root
yarn install                                    # install dependencies
yarn build                                      # build @toio/* packages
yarn example:<name of example>                  # start sample application (see below)
```

If `yarn` command is not existed, type `npm install -g yarn` to install.

### List of sample application

| Name & Source                                   | Command                         | #cubes | Mat | Description                     |
| ----------------------------------------------- | ------------------------------- | ------ | --- | ------------------------------- |
| [id-reader](./examples/id-reader)               | `yarn example:id-reader`        | 1      | Yes | read & show toio ID information |
| [keyboard-control](./examples/keyboard-control) | `yarn example:keyboard-control` | 1      | No  | move a cube with ↑↓←→           |
| [chase](./examples/chase)                       | `yarn example:chase`            | 2      | Yes | a cube chase another one        |