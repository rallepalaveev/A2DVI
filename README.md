# A2DVI

This is a project based on the AppleII-VGA and Pico-DVI-Sock projects.

Ideally, if successfull it will run firmware, which would have switchable video output to one of the VGA or HDMI ports at a time.
So far the board has been designed with the impedance calculations for the HDMI port - to be honest, my first attempt, I hope I got that right.
The first step is to make the original firmware work via the VGA output, which should not cause any troubles.
After that the firmware for the HDMI part needs to be developped.
The project might even produce a card with both VGA and HDMI operational simultaneously (2xPico cluster?)...

Copyright (c) 2024 Ralle Palaveev
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
