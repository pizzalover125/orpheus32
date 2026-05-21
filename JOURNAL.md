### 5/18: rev 1 (3hrs)
- During highway, Jenin had this idea to make an ESP32 devboard called Orpheus32, but ended up never making it and granted me permission to make it
- I never made it... until now!
- im going to use KiCad
- going to use WROOM-32
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

### 5/19: rev 3 (3hr)
- @Rudy on Slack told me to use a ESP32 with built-in UART-to-USB
- ig thats what we are doing for this
- after brief research, I found ESP32-S3-WROOM-1 with 36 GPIO
- will read https://documentation.espressif.com/esp32-s3-wroom-1_wroom-1u_datasheet_en.pdf
- idk if I even should create a board bc its going to be super basic
- copied USB-C w/o diode
- going to use same power circuitry
- added buttons

<img width="894" height="453" alt="image" src="https://github.com/user-attachments/assets/75027cbf-4164-4623-b277-2190b0d887d3" />

- bruh my schematic feels so basic

<img width="624" height="511" alt="image" src="https://github.com/user-attachments/assets/6f2edb70-1740-4331-844c-920b3495b826" />

- pcb also feels too basic... idk if this is worth it cause its too basic

- ok im back after a couple of hours
- i'm going to make this a sensor board
- finally mastered differential pairs in KiCad w https://www.youtube.com/watch?v=M13QxtPVrXY!
- wait routing this is impossible

<img width="621" height="317" alt="image" src="https://github.com/user-attachments/assets/4cffa2c9-d276-4f96-a219-0fe059598b45" />

- waiting for expert resposne in Slack; going to select some chips to use
- after brief research, i've decided to use BME280 and LSM6DS3
- BME280 is temperature, while the LSM6DS3 is accelorometer

<img width="245" height="446" alt="image" src="https://github.com/user-attachments/assets/c572c9c6-f3a2-45c6-98ca-aa34ce1d59c8" />

- after much reading of datasheets, came up with this! hopefully it is correct

<img width="390" height="589" alt="image" src="https://github.com/user-attachments/assets/4757f6ed-9268-40a3-93fd-0c8d4ca00880" />

- rev 3 is complete!

### 5/20: rev 3.1 (2hr)
- I fixed DRC errors that Taran pointed out
- now i want to add a neopixel to make it look cooler
- going to use SK6812 cause why not
- routed it!
- will add 3d model
- ok added it from SnapEDA
- wait the headers are reversed; need to fix

<img width="672" height="583" alt="image" src="https://github.com/user-attachments/assets/5ce3f394-bfdb-4f78-a05f-3cce2865ecda" />

- time for silkscreen
- raygen wants me to add another neopixel
- was not planning to, but sure
- added!

<img width="440" height="572" alt="image" src="https://github.com/user-attachments/assets/71542ee3-c655-4b03-8763-db6884ba87c5" />

 - going to view other devboards
 - notes from other breadboards:
   - label schematic to make it pretty
   - label pins (seems to be very important)
   - hack club logo + other silkscreen art
- ok im locked in now
- wow this is harder than I expected
- first half done! one more half to go
- had a bunch of problems choosing font and positioning properly

<img width="375" height="460" alt="image" src="https://github.com/user-attachments/assets/e8078a52-e57e-4446-b389-fb19cd0ba0d3" />

- made post on Hack Club Slack
- ok i think thats it for now; will come back to fix  problems, tidy schematic, and prepare to submit!
- seems like no major errors as nobody has said much on Slack
- Taran told me to add which GPIO are being used for sensors, so I did that!
- going to create order on JLC and source parts!

<img width="419" height="625" alt="image" src="https://github.com/user-attachments/assets/861822b0-5234-448d-ab0d-aa9bee6c105b" />

- im doing everything except the pins cause i don't really need them PCBA

<img width="663" height="411" alt="image" src="https://github.com/user-attachments/assets/e90b4295-8421-430a-8d69-c0c33131750b" />

- ok i can do a lot of optimization
- but first, i need to fix all the things Rudy mentioned
- ahhh too tired for this; will do tmrw ig

### 5/21: rev 3.2 + rev4 (2hr)
- redoing all the passives
- going to change placement as well

<img width="1161" height="489" alt="image" src="https://github.com/user-attachments/assets/717da15a-6563-4c95-87fa-7a7259df5e17" />

- some changes to values + decoupling caps added
- done with pairs + placement!

<img width="414" height="628" alt="image" src="https://github.com/user-attachments/assets/78408c05-fd5b-4f1a-8ff0-8ed245c4ccc0" />

<img width="508" height="669" alt="image" src="https://github.com/user-attachments/assets/84ff7625-c49d-4fe3-a18a-fc50ee917464" />

- wowoowowowow
- time to see price bc i lessened number of items
- bruh price is $93 now
- $180 w customs and shipping 😢
- I HAVE TO RESTART bc ESP32-S3 is too expensive
- luckily i have rev2 still available which uses

<img width="411" height="529" alt="image" src="https://github.com/user-attachments/assets/a41e1987-02a6-4009-a221-4f1c0a8b72f5" />

- routing time
- wait ill add SK6218-mini
- ok added

<img width="309" height="434" alt="image" src="https://github.com/user-attachments/assets/8be38b3e-0780-48df-978d-fe892f08c593" />

- PCB done! need to add silkscreen now!

<img width="385" height="552" alt="image" src="https://github.com/user-attachments/assets/eaf97c20-b58c-4cd7-8e42-e9358d3ad869" />

- both sides done!
- time to add Hack Club logo

<img width="450" height="511" alt="image" src="https://github.com/user-attachments/assets/8230aeaa-9e12-4cf9-8d19-0d54f8feb748" />

- BOOM!
- ok sent message in slack
- idk i feel like accelorometer is not needed
- i think i might prepare for submission now
