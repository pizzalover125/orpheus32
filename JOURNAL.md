### 5/18: rev 1 (3hrs)
- During highway, Jenin had this idea to make an ESP32 devboard called Orpheus32, but ended up never making it and granted me permission to make it
- I never made it... until now!
- im going to use KiCad
- going to read this https://documentation.espressif.com/esp32-s3-wroom-1_wroom-1u_datasheet_en.pdf
- ok read it; it was very boring but pretty useful about where to place capacitors and stuff
- realized that it doesn't have easy USB pins like RP2040; need a USB to UART coverter
- after some vary minimal research, it looks like CH340C is the standard for the converter
- using LDO AMS117 3.3v edition
- working on USB-C
- need B5819W diode
- adding power LED
- following standard conventions for the first time by having GND face down and VCC/VBUS/+5V/etc face up

<img width="414" height="315" alt="image" src="https://github.com/user-attachments/assets/44e81c30-c35a-4109-902c-ed0f3350d969" />

- USBC done

<img width="288" height="162" alt="image" src="https://github.com/user-attachments/assets/f62bc065-b92a-4dbb-b1b1-91418e096191" />

- LDO done

<img width="274" height="483" alt="image" src="https://github.com/user-attachments/assets/96a9699a-651c-4095-95d1-14cb5396be86" />

- USB to UART done

<img width="289" height="483" alt="image" src="https://github.com/user-attachments/assets/c98441b8-1d0f-4e2f-8319-eb77b06cdf8a" />

- buttons done

<img width="262" height="563" alt="image" src="https://github.com/user-attachments/assets/df33521f-2cf4-48c7-898b-f2ae7c2ce8b2" />

- actual ESP32 + pins done also!

<img width="681" height="520" alt="image" src="https://github.com/user-attachments/assets/db03043c-679e-4c44-ad54-a989192b8d45" />

- ok assigned footprints
- will start PCB now... wow this project is super easy thus far

<img width="443" height="212" alt="image" src="https://github.com/user-attachments/assets/59429547-d595-4671-b43b-f5ea0a49f5f7" />

- got general layout sort of... need to add components

<img width="857" height="624" alt="image" src="https://github.com/user-attachments/assets/6571d519-26c3-45cf-b68f-a830a080f495" />

- components added
- time to route
- ill use differential pair
- surprisingly not too difficult
- bruh i messed up schematic
- ok i added ground planes and am done with rev1!
- ill get a 3d model of the USBC first

<img width="654" height="475" alt="image" src="https://github.com/user-attachments/assets/3fbc79ac-e92a-4ebd-8b1a-e40a859dff09" />

- ok time to find bugs and do more revisions!

### 5/18: rev 2 (2hrs)
- time to fix everything I did wrong, such as:

<img width="363" height="175" alt="image" src="https://github.com/user-attachments/assets/0aa66358-7195-4cc3-9b9f-fc69c958fff8" />

- also apparently my routing is inefficient

- REROUTED EVERYTHING AGAIN BUT IT STILL DIDN"T WORK
- AHHHHH

<img width="759" height="507" alt="image" src="https://github.com/user-attachments/assets/45149e4d-0925-4d52-ac21-19b0cc0631f8" />

- time to watch https://www.youtube.com/watch?v=KgOQaBUPiBo
- ok that vid no good lets try https://www.youtube.com/watch?v=v2okbB05piE
- AI slop vid; nvm lets try https://www.youtube.com/watch?v=0tuuMSxcVxg
- got it working!

<img width="604" height="419" alt="image" src="https://github.com/user-attachments/assets/b54e11d2-54d0-4d2d-9c33-5c1cb2f54dfa" />

- w render
- and we are done with routing for rev2... wow this is turning out great! next rev, need to minimize vias from 15 to like 5

<img width="724" height="521" alt="image" src="https://github.com/user-attachments/assets/a5b7a68e-b5ad-479a-b604-017c4db5f8b2" />

