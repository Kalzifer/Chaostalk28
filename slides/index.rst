=================================================
ChaosTalk#28
=================================================

.. revealjs:: Herzlich willkommen

  .. image:: _images/28-poster.png
    :target: "#"
    :class: image
    :width: 450
    :height: 636
    :alt: ""	
	
	
.. revealjs:: Übersicht
	
	* Arduino Projekt
	* Arduino Hardware
	* Arduino IDE
	* PlatformIO Core
	* Atom
	* Hands-On
	
.. revealjs:: Arduino Projekt

  * Seit 2005 
  * Entwickler: Massimo Banzi & David Cuartielles
  * bis 2008 ca. 50.000 Boards verkauft
  * 2015 Rechtsstreit um die Marke Arduino
	
.. revealjs:: Arduino Hardware

 .. list-table::
   :header-rows: 1

   * - Controller
     - Boards
   * - ATmega 328
     - 12
   * - ATmega 32u4
     - 4
   * - ARM Cortex M0
     - Arduino Zero
   * - ARM Cortex M3
     - Arduino Due
   * - Quark x86
     - Genuino 101


.. revealjs:: Arduino IDE

  * Basis Processing
  * JAVA 
  * Serial Terminal stürzt gerne mal ab
  * Keyword-Lists für Libraries
  * IDE versteht C/C++ nicht

.. revealjs:: PlatformIO Core

  * Unified Debugger
  * Remote
  * Unit Testing
  * Continuous Integration

.. revealjs:: PlatformIO Core Install

  .. rv_code::

    pip install -U platformio

.. revealjs:: Playground 
  :title-heading: h2
  :subtitle: Boards
  :subtitle-heading: h4
 
  .. rv_code::

   # Alle Boards auflisten

   platformio boards

   > Platform: atmelavr
   > --------------------------------------------------------------------------------
   > ID                    MCU            Frequency  Flash   RAM    Name
   > --------------------------------------------------------------------------------
   > bluefruitmicro        ATMEGA32U4     8Mhz      28kB    2.5kB  Adafruit Bluefruit
   > feather32u4           ATMEGA32U4     8Mhz      28kB    2.5kB  Adafruit Feather
   > flora8                ATMEGA32U4     8Mhz      28kB    2.5kB  Adafruit Flora
   > ...


.. revealjs:: Playground 
  :title-heading: h2
  :subtitle: Boards Filter
  :subtitle-heading: h4

  .. rv_code::

   # pio boards [OPTIONS] [FILTER]

   pio boards ATMEGA32U4

   > Platform: teensy
   > --------------------------------------------------------------------------------
   > ID                    MCU            Frequency  Flash   RAM    Name
   > --------------------------------------------------------------------------------
   > teensy20              ATMEGA32U4     16Mhz     31kB    2.5kB  Teensy 2.0

.. revealjs:: Playground 
  :title-heading: h2
  :subtitle: Projekt erstellen
  :subtitle-heading: h4

  .. rv_code::

    platformio init --board uno --board nodemcuv2 --board teensy31

  .. rv_code::

    Resultat: platformio.ini

    [env:uno]
    platform = atmelavr
    framework = arduino
    board = uno

    [env:nodemcuv2]
    platform = espressif8266
    framework = arduino
    board = nodemcuv2

    [env:teensy31]
    platform = teensy
    framework = arduino
    board = teensy31
	
.. revealjs:: Playground 
  :title-heading: h2
  :subtitle: main.cpp
  :subtitle-heading: h4

  .. rv_code::

    vim src/main.cpp

  .. rv_code::

    #include "Arduino.h"
    void setup()
    {
		// initialize
    }
    void loop()
    {
		// main loop
    }
	
.. revealjs:: Playground 
  :title-heading: h2
  :subtitle: Build & Upload
  :subtitle-heading: h4

  .. rv_code::

    platformio run --target upload
  
.. revealjs:: Atom

  * C/C++ Intelligent Code Completion
  * C/C++ Smart Code Linter for rapid professional development
  * Library Manager for the hundreds popular libraries
  * Multi-projects workflow with multiple panes
  * Themes support with dark and light colors
  * Serial Port Monitor
  * Built-in Terminal


.. revealjs:: Hands-On HINWEIS

  .. rv_code::
    
    Linux Users:
    Ubuntu/Debian users may need to add own “username” to the “dialout” 
    group if they are not “root”, doing this issuing a 
    
    sudo usermod -a -G dialout yourusername.

    Install “udev” rules file 99-platformio-udev.rules 
    (an instruction is located in the file).
    Raspberry Pi users, please read this article Enable serial port on 
    Raspberry Pi.

    Windows Users: Please check that you have correctly installed 
    USB driver from board manufacturer

    https://github.com/platformio/platformio-core/blob/develop/scripts/99-platformio-udev.rules 

.. revealjs:: It's dangerous to go alone!
  :subtitle: take one of these
  :subtitle-heading: h3

  .. raw:: html
	
	<tr>
		<td><img src="_images/atom.png" alt="" border=0 height=128 width=128></img></td>
		<td><img src="_images/emacs.png" alt="" border=0 height=128 width=128></img></td>
        <td><img src="_images/cloud9.png" alt="" border=0 height=128 width=128></img></td>
        <td><img src="_images/vim.png" alt="" border=0 height=128 width=128></img></td>
        <td><img src="_images/che.png" alt="" border=0 height=128 width=128></img></td>
    </tr>

  http://docs.platformio.org/en/latest/ide/atom.html
  
.. revealjs:: Quellen

  * http://docs.platformio.org/en/latest/
  * https://www.arduino.cc/
  * https://de.wikipedia.org/wiki/Arduino_(Plattform)
  * https://atom.io/
  
.. revealjs:: Erstellt mit

  Sphinx
  
  * http://www.sphinx-doc.org
  
  sphinxjp.themes.revealjs
  
  * https://pypi.python.org/pypi/sphinxjp.themes.revealjs/

