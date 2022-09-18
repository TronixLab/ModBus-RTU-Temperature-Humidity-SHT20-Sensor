This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.

1.Description
QModMaster is a free Qt-based implementation of a ModBus master application. A graphical user interface allows easy communication with ModBus RTU and TCP slaves. QModMaster also includes a bus monitor for examining all traffic on the bus.

2.Software
QModMaster is based on libmodbus 3.1.0-1 <http://www.libmodbus.org/> for modbus communication and on QsLog <https://bitbucket.org/razvanpetru/qt-components/wiki/QsLog> for logging. Supports both Windows and Linux.

3.Source code is availiable for Windows and Linux for compilation using Qt 5.2.1 <http://www.qt.io/download/> . Install Qt on your system,open QModMaster project file (QModMaster.pro) and compile.

4.For Windows a pre-compiled binary is availiable. It does not require instalation, just unzip and run.

5.To configure the logging level set the 'LoggingLevel' in QModMaster.ini file
- TraceLevel : 0
- DebugLevel : 1
- InfoLevel  : 2
- WarnLevel  : 3 [default]
- ErrorLevel : 4
- FatalLevel : 5
- OffLevel   : 6