# QMK Anne Pro 2

Repository dedicated to my custom QMK config for Anne Pro 2.

**Version**: C18

## References 
* [Open Anne Pro](https://openannepro.github.io)
* [QMK Firmware](https://qmk.fm)
* [QMK Configurator](https://config.qmk.fm/#/annepro2/c18/LAYOUT_60_ansi)

## Install Anne Pro Tools

1. Install the latest stable rust toolchain using [rustup](https://rustup.rs/).

    > On Windows: also install Visual Studio Community edition including the C/C++ module to prevent errors while compiling on step 6 below.

    > On Linux: make sure following software/packages pkg-config pkgconf libusb-1.0-0 libusb-dev are installed to prevent errors while compiling on step 6 below. If not, install them with `sudo apt-get install pkg-config pkgconf libusb-1.0-0 libusb-dev`

    > You might need to run below command to configure the right path for pkgconfig do its work on step 6 below.
`export PATH_CONFIG_PATH=/usr/lib/x86_64-linux-gnu/pkgconfig/`

2. Clone the AnnePro2-Tools project:

    ```Bash
        git clone https://github.com/OpenAnnePro/AnnePro2-Tools.git
        cd AnnePro2-Tools
    ```

3. Compile:

    ```Bash
        cargo build --release
    ```

> The compiled tool should be in `./target/release/annepro2_tools`

## Generate QMK keymap

Use [QMK Configurator](https://config.qmk.fm/#/annepro2/c18/LAYOUT_60_ansi). Optionally load the json file from the version you want to customize.

## Flash process 

1. Enter IAP mode:
    * Unplug USB cable;
    * Plug USB cable while holding <kbd>ESC</kbd> key.

* Flash QMK firmware
    ```Bash
        .\annepro2_tools annepro2_c18_default.bin
    ``` 

* Flash Shine (Optional)

    ```Bash
        .\annepro2_tools --boot -t led annepro2-shine-C18.bin
    ```