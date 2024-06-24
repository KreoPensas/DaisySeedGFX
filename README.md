# DaisySeedGFX
TFT graphical display library for Daisy Seed. ST7789 and ST7735 driver

## Author
DAD Design  (edits and translation by Kreopensas)

## Présentation
DaisySeedGFX is a graphics library for Electrosmith's Daisy Seed platform.
The library currently only supports ST7735 and ST7789 controllers. The library should be able to be adapted to any controller quite easily.

The library uses an intermediate frame buffer between the graphics primitives and the controller. The modifications made in the frame buffer are transmitted to the controller using SPI transfers under DMA. In order to reduce transfers the frame buffer is divided into blocks -> only modified blocks are transferred to the screen.

The graphic primitives are minimalist, they can be supplemented according to needs.


## Mise en oeuvre
The code can be modified and compiled under VS Code in the Daisy Seed development environment (see https://github.com/electro-smith).

### Configuration
Create a project with the helper.py tool (or other...).
Clone the library into the DaisySeedGFX folder inside your project folder.
Edit the Makefile and add DaisySeedGFX/Frame.cpp DaisySeedGFX/GFX.cpp DaisySeedGFX/TFT_SPI.cpp in the CPP_SOURCES line.
Copy the UserConfig.h file into your project folder and configure it according to your screen and the pins used.

### Fonts
To create fonts use the tool https://rop.nl/truetype2gfx/. Each font is saved as an xxx.h file.

### Exemples
Examples of implementation are given in the repositories:
1. https://github.com/DADDesign-Projects/DEMO_DaisyGFX_ST7735
2. https://github.com/DADDesign-Projects/DEMO_DaisyGFX_ST7789
