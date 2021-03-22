
                         Simple DirectMedia Layer

                                  (SDL)

                                Version 2.0

---
https://www.libsdl.org/

Simple DirectMedia Layer is a cross-platform development library designed
to provide low level access to audio, keyboard, mouse, joystick, and graphics
hardware via OpenGL and Direct3D. It is used by video playback software,
emulators, and popular games including Valve's award winning catalog
and many Humble Bundle games.

More extensive documentation is available in the docs directory, starting
with README.md

Enjoy!
	Sam Lantinga				(slouken@libsdl.org)
	
	
	
Building modified SDL2 OGS from source instructions:

Install GPU development headers and library:
CODE: SELECT ALL

wget https://oph.mdrjr.net/meveric/pool/go2/libm/libmali-rk/libmali-rk-bifrost-g31-rxp0-gbm_1.7-2+deb10_arm64.deb
wget https://oph.mdrjr.net/meveric/pool/go2/libm/libmali-rk/libmali-rk-dev_1.7-1+deb10_arm64.deb
sudo apt install ./libmali-rk-dev_1.7-1+deb10_arm64.deb ./libmali-rk-bifrost-g31-rxp0-gbm_1.7-2+deb10_arm64.deb

Get Dependencies:
sudo apt-get install libx11-dev libsm-dev libxext-dev git cmake mercurial libudev-dev libdrm-dev zlib1g-dev pkg-config libasound2-dev libfreetype6-dev libx11-xcb1 libxcb-dri2-0


Checkout the source and build SDL2 with KMSDRM support:
CODE: SELECT ALL

cd ~
git clone https://github.com/AreaScout/SDL.git
cd SDL
./autogen.sh
./configure --disable-video-opengl --enable-video-kmsdrm
make -j3
sudo make install
