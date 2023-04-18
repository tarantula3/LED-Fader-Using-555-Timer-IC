# LED-Fader-Using-555-Timer-IC

[![AQhBpQrfmg8](https://i.imgur.com/5AI7Q4q.jpg)](https://www.youtube.com/watch?v=30wGujPnupw)

Wanted to generate a LED fading effect (fade-in and fade-out) for my upcoming video tutorial using the 555 timer IC.
I already have a video where I used LM358 Dual Operational Amplifier IC and another one with Arduino to generate the LED fading effect.

YouTube, is full of video showing how to generate the fading effect using 555 timer IC. However, none of them produce a true fading effect. 
Some just fades-in but never fades-out. And there is literally no explanation of how they are generating the fading effect other than just showing how to assemble the components.

In this tutorial, I am going to show you guys how to create a true LED fading effect using the 555 timer IC. I will also explain how the circuit works and how changing components change the fading effect of the LEDs.

Video: https://www.youtube.com/watch?v=30wGujPnupw


Components Required
-------------------
![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgOz0wyyaN03NbdhGI7GzxS1lkuE6uMGXtHuzYCdO2xwHryP4oiJ5npXO7jRuzihIEDn_Jf5vhWGHbgNaGM9u9EYzJ6SMmRkMHXtbk-Ai3aJhMGeEItiv103XMO9CNs_GkNYA3eLMusXYJ4cp9sq02SD-o_6pzS-nOIStvs7u2ALVUe60mAiYta89Uy/s1054/4.png)

For this tutorial you need:
1 x 555 Timer IC
1 x 47KΩ Resistor
1 x 220Ω Resistor
1 x BC548 NPN Transistor
1 x 33µF Capacitor, and
1 x Few Blue LEDs


Circuit Diagram
---------------
![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhqzlZrGyeogJOx8ZeTGpCqL6FjgJ5rWoNd7LdCei4W1OSQXu_9OUwiBKMY0E2AJsBcQodenPp-P76cCxlmP_cKtf4kT_aUjUuLA-yUTkDK9_qIrF742xu9_6pKgDLLOn_W3aUmHZN-YyVIIN8ul6miiKk3x-ZA0ADIu4P_udmb7tbzyjTCMIwODYvx/s1054/12.png)

The heart of this circuit is the 555 timer IC.
Pin No.1 of the IC is connected to GND.
By connecting Pin 2 and 6 of the 555 timer IC, we put the IC in astable mode. In astable mode, the 555 timer IC acts as an oscillator (re-triggering itself) generating square waves [PWM Signals] from the output Pin no. 3.
3 other components connect to this junction. 
1st one is the 33µF capacitor. The positive pin of the capacitor connects to the junction and the negative pin is connected to the GND.
2nd one is the 47KΩ resistor. One of its legs connects to the junction and the other leg connects to the Output pin, Pin No.3 of the IC.
3rd one is the Base of the BC548 NPN transistor. The collector of the transistor along with Pin 8 and 4 of the IC connects to the +ve terminal. of the battery. The LED along with its current limiting resistor is connected to the Emitter of the transistor.
That's it as simple as that. 

Alright, now I am going to demonstrate how this circuit works with the help of an animation.


How The Circuit Works
---------------------
![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgKbI8AFSYGq5oKI-fXPbAbcopGf_jPLtsCjmR6JI2cNWMrnNkY65fjf0DrIxYECRwZjFy6ZIdn-w50myIoaffGR2RKiQGKq8tNKV7fRUghug7_N7fGYaZMKyBfrwW3vdvfpx6PL6Y8X8_Qih-pHvwTxHhbtMbwJosguEF-MKt7RMgYUjna-2sjZNYV/s1054/6.png)

* When Pin 2 of the IC detects voltage LESS than 1/3rd of the supply voltage, it turns ON the output on Pin 3.
* And, when Pin 6 detects voltage MORE than 2/3rds of the supply voltage, it turns OFF the output.

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhGusssxoPIIkR8rgy67y0I4yoOvm_FlrS1108j_X2oH6qEqrIQxrt6N4hu90fm_BaORDNDKGb3QMyAdrEJwYmfkwpl1BYrnItHQujgFXWNm076xLw3KJkuiE_IRqN7B3uDD2xOFVwf03TizOAgZHjo1ml93bVO2HsJzUldpL7vrv3MKxbXUL8EUvoJ/s1054/7.png)

This is how the trigger pin (Pin2) and the threshold pin (Pin6) of the 555 timer IC sense voltages and controls the output at Pin 3.


![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiufJxn8HpUxkInlFzPCXAeihB128xlnTwUGOs9_1tXjxrP6v9Oq_gi2UV5jgSdvMoOFjHB50uixACjc9B5aam4wAZvyxNwYmqvBA9U6IdWbGujHkGz3EeK1mUQKq6Md6PDhWIPRlOPpFRrP20O92x2auQQLN126xrt2fk3WBNYcUTAYdR-iB6oWWsg/s1054/8.png)

* The Capacitor attached to the circuit will be in a discharged state immediately after firing up the circuit. 
* So, the voltage at Pin 2 will be 0v which is less than 1/3rds of the supply voltage, this will turn ON the output on Pin 3.
* Since Pin 3 is looped back to Pin 2, it will start charging the Capacitor via the 47KΩ resistor.
* At the same time the base current of the transistor also increases causing the LED to slowly "fade-in".
* Once the voltage across the capacitor crosses 2/3rds of the supply voltage, Pin 6 turns OFF the output.
* This causes the capacitor to slowly discharge causing the base current to fall and hence the LED starts "fading-out".

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgXmj_C1D0spOzfk0vFAIzWn2pl2Vnb4x3oUO9oRc-HqLGvLc8e9Ge0_bnpJYP40ghMJUdheSl-3zbcp92-jFYSj_0KzJYUduf8DjmPJV_EAolqoipOtGayVkCXuqr11H28HRp058o0WKJI_GuseZOMU6m2t_N5PVBMSpMRCbUxYp1FmoMypuWbRT72/s1054/9.png)

* Once the voltage across the capacitor falls below 1/3rd of the supply voltage, Pin 2 turns ON the output, and the above cycle continues.
You can hook up a multimeter to the circuit to measure the charging and discharging of the capacitor.


Breadboard Demo
---------------
![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiWiSX6y3l-JCK-7p-GZghPxFkVWZZXDEwI7TKW01YV9Q9uomjHFH6ETh18VzTaULUXH2a4ijEbshj6SRNIhayK3FZkxT2_93pAffFxmD0wkx-MEMU81SXVEilXdtYx6leoGOsmTVwGS3v6905rQPBkSyy6A6DQgYysCCWkYvh4rwYJF5zGe2GeQ8-D/s1054/10.png)

So, here is a quick demo on a breadboard.
In the current setup I have a 33µF Capacitor and a Blue LED on the breadboard.
Replacing the 33µF Capacitor with a 100µF Capacitor makes the LED fade in-and-out slower as the 100µF capacitor charges and discharges slower than 33µF Capacitor.

Also by replacing the "Blue LED" with a "Red LED", we can make the LED to stay "on" longer than the blue one with the same value of capacitor. This is because the "Forward Voltage" (Vf) of the Blue LED is higher than that of the Red LED. 
"Forward voltage" is the minimum amount of voltage that is required to allow an electrical component to turn on.
The red, green and yellow LEDs have relatively "low" forward voltage ranging from 1.6-2.2V and hence stays on longer when the capacitor slowly charges or discharged. However, blue and white LEDs starts conducting from 2.5-4V and hence, when the discharging capacitor's voltage hits the threshold the LED turns off faster than the other colors. I have provided a link to how the forward voltage works in the description below.
If you connect few LEDs in series, the forward voltage adds up and hence it will require more voltage to turn on the LEDs.

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhTovIXj-H2eZ5SGECRhVtcacYTze8oCw-xo6C6J9Boe6Rg3nQXFii2KaZVB8BiJxZ6s4b66nmDSIi7rpyJDVwSdmdbzjk4ipppU9lKThjDXsUde6RnlgEHf3S_0WsFR2NIT7OsGFvIrsfwH9VEblm0d-DvZbx8p96jPNgJZBWaEkt2jXQqSFCZKv5Q/s1054/11.png)

You need to add a current limiting resistor between the emitter of the transistor and the LED to avoid an internal short-circuiting inside the led.


The Board
---------
![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjylNxsTiApGX6k4j_BRie37oq2czDO3XXu2iwTydZeAsP-qSEcSS18qLkgwEjzNo_rdGOsSqPgzrE2UWLcrQhYvQEA_sh5bbYmzTISo73-KL69JIxrXGFOdFXs_IASBHjcvdqHL9B24y9GMQvPR4hrNIgENR-AlH_eV2YV8bD9pfoR-feeVuafW0Wy/s1054/13.png)

To make it easy for you guys, I have created this tiny little "555 LED Fader Module". After assembling the components, you just need to power this module by providing a voltage between 5v to 15v to fade the LED.

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjST4-vOQfTvWNw9DvO4e6udxEK0kFPg6-JGByLjEsC7V9S0sYtZt95HumJWCpDCgtZnWOwEXRqn6RFL4KBgimvPvdLnQv572yDpNEYlZqCryOOSR7CrZUwqB0_ceeYG4GHGBXRC-lpZrTy3Mwk4lcjAJpCM8JNyU1fGvDkoyPqW9JKKYwd1tkL1Sqd/s1054/14.png)

So, this is how my board looks like in 2D and 3D. There are 16 breakout boards in this 100cm x 100cm assembly. You can download the gerber file from the link provided in the description below and order it from PCBWay.


Soldering
---------
![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgElOyxK2mJBkQrtD2dKei5fFW-5JbE1QQ8KABC0c4AJL5yLnMiBODB_n1lxy_YtJGm9SOh1t2U2PHirJEdtSJsPcworNl4mhXL-9qGRDxbb89zQ2Jeb0qvaRvofvdEIa6o2pj00O27OOJQDZJ88A813XphNHxxaoAHTlF8tCQH_X1WwgSQ1qpj9I4i/s1054/15.png)

Let me quickly show you guys how to assemble the components to this custom made board.
Let's start by soldering the IC Base to the board. 
Then let's solder the two resistors to the board. Next, lets solder the capacitor followed by the transistor to the board. Then, lets solder a blue LED to the board.
Once done, let's insert the 555 timer IC to the IC base.
To conclude the setup, I soldered 2 x Female pin headers to the board. You can either solder a pair of female pin-header or male pin-header or solder a pair of wires directly to the board to power this module.

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh6f6RXHPeRtTF1cXJrjuXDOVU7na5-ARM_Yk8h2U2vb9Pa50sTyVtH7tkLA450SEpArXS0tkneM1L7py6THu71qbys7BhZkoCbebv_5D9BCinhOZLQELfy7CUYKj5auC_NUG_A6HAFseTlLhrjkSJG9wgNOBTiR1Z4VrLD-8-L0Nd8SFGmU-G1uVs1/s1054/18.png)


Demo
----
![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjwMvz60v4_Mkh0T8n-8uBPfBwydsqoWXUejvwdBnhp3HObf6QaeYLD0Z66GKKSRV_pyUNRbPGlPuZYlxjE2peIUbkqvT0Y2gD_CJoXm3OLPMCLqjM8pdd9g8PLTs9nkLA7H_MHPLb983WFgvbLE4yqXY8IEjTvpWUFFNVES3BB_JTtgthLZxbg5aNM/s1054/19.png)

Cool, so this is how my module finally looks like.
You can install female pin-headers in-place of the LED or Capacitor if you plan to use this as a development/testing board instead of a module.

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi0juxxDCRluO6bzyn6Jqm-DwTkMMxx3dFdJZtRKQrnU8dqx7bqkCnZbB7nLXQV7PSrUv9FEk09oTiwk7ugXyW0ky-SajmjKvGUSuE7rJMMGJcRqp64ox04EeKl9o9AltGmVcD68FbWRAnZSozqWDRhKdYeJTOtnlgA-eYSwfuI82Q7aVFePyEI26cC/s1054/20.png)


Thanks
------
[![AQhBpQrfmg8](https://i.imgur.com/5AI7Q4q.jpg)](https://www.youtube.com/watch?v=30wGujPnupw)

Thanks again for checking my post. I hope it helps you.
If you want to support me subscribe to my YouTube Channel: https://www.youtube.com/user/tarantula3

Video: https://youtu.be/30wGujPnupw

Full Blog Post: https://diyfactory007.blogspot.com/2023/04/555LedFader.html


LED Fader - With or Without Arduino: Visit https://youtu.be/IIUsdICycOw

Adjustable Single/Dual LED Flasher Using 555 Timer IC: Visit https://youtu.be/B1URFJywtcI



**Other Links:**

Gerber: Visit https://www.pcbway.com/project/shareproject/LED_Fader_Using_555_Timer_IC_76bb4769.html

Github: Visit https://github.com/tarantula3/LED-Fader-Using-555-Timer-IC

Simulation: Visit https://tinyurl.com/2qv266bg

What Is Forward Voltage: Visit https://42electronics.com/blogs/learn-more/what-is-forward-voltage



**Support My Work:**

BTC:   1Hrr83W2zu2hmDcmYqZMhgPQ71oLj5b7v5

LTC:   LPh69qxUqaHKYuFPJVJsNQjpBHWK7hZ9TZ

DOGE:  DEU2Wz3TK95119HMNZv2kpU7PkWbGNs9K3

ETH:   0xD64fb51C74E0206cB6702aB922C765c68B97dCD4

BAT:   0x9D9E77cA360b53cD89cc01dC37A5314C0113FFc3

LBC:   bZ8ANEJFsd2MNFfpoxBhtFNPboh7PmD7M2

COS:   bnb136ns6lfw4zs5hg4n85vdthaad7hq5m4gtkgf23 Memo: 572187879

BNB:   0xD64fb51C74E0206cB6702aB922C765c68B97dCD4

MATIC: 0xD64fb51C74E0206cB6702aB922C765c68B97dCD4


Thanks, ca again in my next tutorial.


Tags
====
LED Dimmer, led fader, led fader without Arduino, PWM LED Dimmer Using NE555, LED Fader, fader, PWM LED Dimmer, breathing LED, 555 Project, LM358 Project, pwm, Pulse Width Modulation,LM358,operational amplifier,analogWrite,Breadboard,square wave, triangle wave, Adjustable Single/Dual LED Flasher Using 555 Timer IC,LED Flasher, 555 LED Flasher,555 Pulse Generator,Frequency Adjustable Pulse Generator Module,astable mode, oscillator,555 Module, Pulse Generator Module NE555 Chip


YouTube: https://www.youtube.com/watch?v=30wGujPnupw
Rumble:  https://rumble.com/v2iqxk8-led-fader-using-555-timer-ic.html
Odysee:  https://odysee.com/@Arduino:7/LED-Fader-Using-555-Timer-IC:8
Cos:     https://cos.tv/videos/play/43832864654529536


