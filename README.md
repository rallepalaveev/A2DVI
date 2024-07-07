# A2DVI

This is a project based on the AppleII-VGA and Pico-DVI-Sock projects. It is a video output card for Apple2 compatible computers with 2 supported video modes: VGA or HDMI.

The card can run one mode or the other, but not both simultaneously. To switch between modes, a firmware update is required and opening/closing connections.

For the DVI output to be active, the new firmware developped by (c) 2024 Thorsten Brehm should be used.

Procedure to activate DVI mode:
* v1.5:
  program A2DVI firmware to RPI Pico;
  open all 9 DIP switches.
* v1.6:
  program A2DVI firmware to RPI Pico;
  desloder the 8 soldering pads at GPIOs 14-21.

For the VGA output to be active, the standard firmware developped by (c) 2024 Mark Aikens should be used.

Procedure to activate VGA mode:
* v1.5:
  program VGA firmware to RPI Pico;
  close all 9 DIP switches.
* v1.6:
  program VGA firmware to RPI Pico;
  sloder the 8 soldering pads at GPIOs 14-21.

The pin on the board is for AltChr connection, supported bt A2DVI firmware for alternatiche character sets on non-US versions of Apple2.

Board design by (c) 2024 Ralle Palaveev.

All rights reserved.

Redistribution and use in source, binary, and manufactured forms, with or without
modification, are permitted provided that the following conditions are met:
1. Redistributions of source code and design files must retain the above copyright
   notice, this list of conditions and the following disclaimer.
2. Redistributions in binary or manufactured form must reproduce the above copyright
   notice, this list of conditions and the following disclaimer in the
   documentation and/or other materials provided with the distribution.
3. All advertising materials mentioning features or use of this software
   or hardware must display the following acknowledgement:
   This product includes software or hardware developed by Ralle Palaveev.
4. Neither the name of Ralle Palaveev nor the
   names of its contributors may be used to endorse or promote products
   derived from this software or hardware without specific prior written permission.

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
