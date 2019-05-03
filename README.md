# LM386 based audio amplifier for raspberry pi zero


This is a lm386 based amp designed for rpi0. As rpi0 does not have an audio output jack like the rpi b or rpi a another option is needed. There are three options: last two being an usb sound card and i2s sound board which are both comparatively expensive and add more bulk to your project. First choice is gpio sound output. But gpio sound output is a it problematic that is: it is very noisy. To suppress noise a band pass filter consisting a low pass filter and a high pass filter is used. Filtered output is weak so an amplifier is necessary. Amplifier of choice is PAM8403 based stereo amp board which is both cheap and small. 

Although PAM8403 is likely most used amp in diy projects as i already had lm386 ic i decided to use it. So i designed a compact pcb in eagle based on lm386 for fitting in an diy handheld gaming console housing. I used http://www.circuitbasics.com/build-a-great-sounding-audio-amplifier-with-bass-boost-from-the-lm386/ and LM386 datasheet as references. If you decide to use this project remember while PAM8403 is a class D amplifier LM386 is a class B amplifier. So it is likely PAM8403 is more energy efficient.

I have already mentioned the noise and despite band pass filter there is unbearable noise to hear acceptable sounds from rpi0 you need to change config.txt in BOOT partition as follows:

<i>
#pwm-audio on gpio 18 and 13
##dtoverlay=pwm-2chan,pin=18,func=2,pin2=13,func2=4
dtoverlay=pwm,pin=13,func=4
disable_audio_dither=1
audio_pwm_mode=1
</i>


<img src="/resim2.jpg" alt="lm386 amp top side" style="width:128px;height:128px;">

<img src="/resim3.jpg" alt="lm386 amp bottom side">

<img src="/pcb.png" alt="pcb design">

<img src="/schematic.png" alt="schematic">
