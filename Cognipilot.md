# Cognipilot
![Cognipilot](assets/cognipilot.png)

CogniPilot is a new class of open source autopilot that can conduct safety critical missions such as public transport, with a level of safety assurance not currently available in other open source autopilots. CogniPilot focuses on state-of-the-art methologies for creating an autopilot with mathematically provable robustness properties.

For more information on how to setup your enviroment and build cognipilot checkout the [Cognipilot developers guide](https://cognipilot.org/)

# Flashing the board

The Teensy comes with its own bootloader, allowing to flash Cerebri through USB.
Teensy provides a Teensy Loader gui flashing for more information checkout their [guide](https://www.pjrc.com/teensy/loader.html)

On Linux you can also flash Cerebri directly from the `west` build system.
To use this method, first install the `teensy-loader-cli` application.
On a Ubuntu based system you can use the following command

```sudo apt install teensy-loader-cli```

Connect the board through USB and then press the physical button on the Teensy to put it into bootloader mode.

Flashing the board is simply done by the command below

```west flash```


On success you should get the following output

```
-- west flash: rebuilding
[1/1] cd /home/peter/cognipilot/ws/cerebri/build/zephyr &&...=/home/peter/cognipilot/ws/cerebri/build/zephyr/zephyr.elf
/home/peter/cognipilot/ws/cerebri/build/zephyr/runners.yaml
flash-runner
-- west flash: using runner teensy
-- runners.teensy: Flashing file: /home/peter/cognipilot/ws/cerebri/build/zephyr/zephyr.hex
```

If Cognipilot has been succesfully flash you should hear a startup tone from buzzer.

# Serial Console 

By default the Cerebri Serial console is provided through `lpuart` on the 6-pin JST-GH connector labeled Debug.
```
                                          ▄▄▄▄▄▄▄▄
         ▄▄▄▄▄ ▄▄▄▄▄                    ▀▀▀▀▀▀▀▀▀
     ▄███████▀▄██████▄   ▀█████████████████████▀
  ▄██████████ ████████ ▄   ▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄
 ███████████▀ ███████▀ ██   ▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀
█████████▀   ▀▀▀▀▀▀▀▀ ████   ▀███████████▀
▀█████▀ ▄▄███████████▄ ████   ▄▄▄▄▄▄▄▄▄
  ▀▀▀ ███████████████▀ ████   ▀▀▀▀▀▀▀▀
       ▀▀█████▀▀▀▀▀▀  ▀▀▀▀   ▄█████▀
               ████████▀    ▄▄▄
               ▀███▀       ▀▀▀
                ▀▀
╔═══╗╔═══╗╔═══╗╔═╗ ╔╗╔══╗╔═══╗╔══╗╔╗   ╔═══╗╔════╗
║╔═╗║║╔═╗║║╔═╗║║║║ ║║╚╣╠╝║╔═╗║╚╣╠╝║║   ║╔═╗║║╔╗╔╗║
║║ ╚╝║║ ║║║║ ╚╝║║╚╗║║ ║║ ║║ ║║ ║║ ║║   ║║ ║║╚╝║║╚╝
║║   ║║ ║║║║╔═╗║╔╗╚╝║ ║║ ║╚═╝║ ║║ ║║   ║║ ║║  ║║
║║ ╔╗║║ ║║║║╚╗║║║╚╗║║ ║║ ║╔══╝ ║║ ║║ ╔╗║║ ║║  ║║
║╚═╝║║╚═╝║║╚═╝║║║ ║║║╔╣╠╗║║   ╔╣╠╗║╚═╝║║╚═╝║ ╔╝╚╗
╚═══╝╚═══╝╚═══╝╚╝ ╚═╝╚══╝╚╝   ╚══╝╚═══╝╚═══╝ ╚══╝
       ┏━━━┓┏━━━┓┏━━━┓┏━━━┓┏━━┓ ┏━━━┓┏━━┓
       ┃┏━┓┃┃┏━━┛┃┏━┓┃┃┏━━┛┃┏┓┃ ┃┏━┓┃┗┫┣┛
       ┃┃ ┗┛┃┗━┓ ┃┗━┛┃┃┗━┓ ┃┗┛┗┓┃┗━┛┃ ┃┃
       ┃┃ ┏┓┃┏━┛ ┃┏┓┏┛┃┏━┛ ┃┏━┓┃┃┏┓┏┛ ┃┃
       ┃┗━┛┃┃┗━━┓┃┃┃┗┓┃┗━━┓┃┗━┛┃┃┃┃┗┓┏┫┣┓
       ┗━━━┛┗━━━┛┗┛┗━┛┗━━━┛┗━━━┛┗┛┗━┛┗━━┛
*** Booting Zephyr OS build zephyr-v3.5.0-3936-g9e01bfe86b7c ***
uart:~$
```
On bootup you should see this Cognipilot banner and then you get a `uart:~$` shell to type your commands
