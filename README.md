# Sample React/TypeScript app for KaiOS 2

This is a hard fork of the KaiOS sample tutorial [sample-react](https://github.com/kaiostech/sample-react).

## Changes

* Technically builds as TypeScript, although it is minimally typed (`strict` is `false`).
* `react-scripts` updated to handle TypeScript/TSX appropriately
* Build changed to work with Node 19.x on Arch Linux

## Development Environment Setup

Tested with a [Nokia 6300 4G TA-1324](https://www.nokia.com/phones/en_us/nokia-6300-4g) and Arch Linux. Buy two of them if you're developing a lot; the only way to test many APIs is with a device / on device tethered to the laptop and you don't want to be doing it with your production phone. Similarly, KaiOSRT is useless for understanding the performance implications of the application on a real device as it's running in Ubuntu.

### Set up a sideload-capable development environment.

1. Download and install `adb` (`pacman -S platform-tools`).
1. Download [PaleMoon 28.6.1](https://archive.palemoon.org/palemoon/28.x/28.6.1/)

### Connect to the device.

1. Start debug mode on the Nokia device by typing `*#*#33284#*#*`. You'll see a bug at the top of the screen.
1. Connect the device to the PC via USB.
1. Check that the device is connected with `adb devices`.
1. Run `adb forward tcp:6000 localfilesystem:/data/local/debugger-socket`
1. Use WebIDE from Developer Tools in PaleMoon.
1. Click "Remote Runtime" and connect to the device at `localhost:6000`.

### Build the application and send to device for testing.

1. Run `yarn run build`.
1. From the WebIDE, choose "Open Packaged App..." and select the `build` folder in this directory.
1. Click the play button in the WebIDE to send it to the device. Ignore the warni*#*#33284#*#*ngs about the date mismatch.
1. Click the wrench to open the debug console if something is going wrong.


## License

KaiOS React/TypeScript Example

Copyright (C) 2023 invariant.

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.