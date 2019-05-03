# LM386 based audio amplifier for raspberry pi zero


This is a lm386 based amp designed for rpi0. As rpi0 does not have an audio output jack like the rpi b or rpi a another option is needed. 
There are three options: last two being an usb sound card and i2s sound board which are both comparatively expensive and add more bulk to your project. 
First choice is gpio sound output. But gpio sound output is a it problematic that is: it is very noisy. To suppress noise a band pass filter 
consisting a low pass filter and a high pass filter is used. Filtered output is weak so an amplifier is necessary. Amplifier of choice is
PAM8403 based stereo amp board which is both cheap and small. 

Although PAM8403 is likely most used amp in diy projects as i already had lm386 ic i decided to use it. So i designed a compact pcb based on
lm386 for placing in an diy handheld gaming console housing.

<img src="/resim2.jpg" alt="lm386 amp top side" style="width:128px;height:128px;">

<img src="/resim3.jpg" alt="lm386 amp bottom side">

<img src="/pcb.png" alt="pcb design">

<img src="/schematic.png" alt="schematic">
