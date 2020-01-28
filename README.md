# VT-IDA Plugin
This is the official VirusTotal plugin for Hex-Rays IDA Pro. This plugin integrates functionality from VirusTotal web services into the IDA Pro's user interface. 

The current version is v0.7beta, This plugin is not production-ready yet, and unexpected behavior can still occur. This release integrates VTGrep into IDA Pro, facilitating the searching for similar code, strings, or sequences of bytes.

## Requirements
This plugin has been developed for **IDA Pro 7.0** and beyond and supports both Python 2.7 and 3.x. 
It requires the "requests" module, the easiest way of installing it is by using ``pip``:

```bash
$ pip install requests
```

## Installation
Copy the content of the ``plugin`` directory into the IDA Pro's plugin directory and start IDA Pro. 

| OS      | Plugin path                                 |
| ------- | ------------------------------------------- |
| Linux   | `/opt/ida-7.X/plugins`                      |
| macOS   | `~/.idapro/plugins`                         |
| Windows | `%ProgramFiles%\IDA 7.X\plugins`       |


## Usage
While in the disassembly window, select an area of a set of instructions and right-click to chose one of the following actions:

* *Search for bytes*: search for the same bytes of the area selected.
* *Search for similar code* : identify memory offsets or addresses in the current area selected and wildcard them.
* *Search for similar code (strict)*: wildcard all the constants defined in the current area.
* *Search for similar functions*: same as "searching for similar code" but automatically selects all the instructions in the current function.

Another option is to look for similar strings. To search for similar ones, open the `Strings Windows` in IDA Pro, right-click on any string (one or many) and select `Virus Total -> Search for string`. 

These actions will launch a new instance of your default web browser, showing all the matches found in VTGrep. Remember that your default web browser must be logged into your VirusTotal Enterprise account in order to see the results.

Check IDA Pro's output window for any message that may need your attention.

Note: This version only supports **Intel 32/64 bits** when searching for similar code. Support for more processors will be added in the next version. 
