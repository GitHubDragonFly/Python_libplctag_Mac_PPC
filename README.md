# PythonTest_PPC
This is a special version of the [PythonTest](https://github.com/GitHubDragonFly/PythonTest), designed for iMac G5 with PowerPC processor.

Currently functional for reading atomic types and their arrays/bits, strings, timers, counters, controls from different PLCs and getting tags from ControlLogix PLC.

Intended to be used solely as a testing tool (not fit for any production environment).

It is using [libplctag](https://github.com/libplctag/libplctag) library v2.3.6 but it also has v2.1.22, both compiled from the source on the iMac itself. You can choose which library to use by editing libplctag.py file and just swapping numbers (just search for 'Power Macintosh' in the file). Using any other version of the library would require that you compile it from the source yourself (which did require small modifications).

The included libplctag.py file was modified to include the 'Power Macintosh' check.

The computer configuration this was tested on: iMac G5 with PowerPC G5 2.1GHz, 2.5GB DDR2 RAM, Mac OS X 10.4.11.

Try experimenting with 64-bit Mac computers by using different versions of the library that you can fetch from the [libplctag](https://github.com/libplctag/libplctag) website.

# Screenshot

![Start Page](screenshots/plctag_gui_ppc.png?raw=true)

# Functionality
- Generally designed to display a single value per tag entered, either of string/integer/float...etc.
- Multiple consecutive elements/bits can be displayed for certain data types by adding "{x}" at the end of the tag, where "x" is the number of elements/bits (ex. CT_STRINGArray[0]{5} or CT_DINT/2{15} or N7:0{3}).
- Displaying bits/PID/Timer/Counter/Control subelement values -> enter your tag, select bit/subelement from available list box (instead of entering it yourself) and optionally add "{x}" at the end.
- Tag status label turns red/green to indicate failure/success in communicating with the PLC. 
- The default values can be changed for the app's startup, check declarations in the top section of the file.
- The app provides automated READ and doesn't include WRITE functionality.
- The "Get Tags" button will fetch ControlLogix tags and double-clicking any of the fetched tags will copy it to the clipboard.
- The IP Address, Path and Tag text boxes offer slightly odd right-click "Paste" functionality.
- The Custom String Length has to be specified when the "custom string" data type is selected.
- Listbox selections are achieved with double-click.
- Modbus functionality of the libplctag library is not included in this app.

There might be bugs in the app. Not everything could be tested by me, since I don't have access to all the different PLCs supported by the libplctag library.
See the libplctag website for all PLCs supported by the library.

The screenshot shows what the app looks like. It reflects libplctag v2.1.17 while the app is currently set to use v2.3.6. Unless something changes in the future versions of the libplctag, the MicroLogix PID will only be available with v2.1.22 and lower.

# Usage

All it takes is to:
- Download and extract the zip file of this project.
- If using the built-in python v2.7.15 then follow the last step to run the file.
- Optionally, if OS X 10.4.11, then install python v3.2.5 on your iMac G5 PowerPC device (available for download [here](https://www.python.org/downloads/mac-osx/)).
- Use either IDLE to open plctag_gui.py file and run it by pressing F5, or use terminal - navigate to your folder - run the file with one of the following commands:
  - `python plctag_gui.py`
  - `python -m plctag_gui`
  - `python3.2 plctag_gui.py`
  - `python3.2 -m plctag_gui`

Note: depending on the python version the graphics might look slightly different and some widgets might need to be resized.

# Licensing
This is licensed under Mozila Public License 2.0+.

# Trademarks
Any and all trademarks, either directly or indirectly mentioned here, belong to their respective owners.

# Useful Resources
Other open source projects with similar app:
- The [pylogix](https://github.com/dmroeder/pylogix) repository.
- The [pycomm3](https://github.com/ottowayi/pycomm3) repository.
