# hl1-scripts
\*some description\*

# Table of Contents
- [Basic scripts](#a-basic-scripts)
  - [Usespam script](#1-usespam-script)
  - [Duckroll/Duckspam](#2-duckroll-aka-duckspam-script)
  - [Fps scripts](#3-fps-scripts)
    - [Hold script](#hold-script)
    - [Toggle script](#toggle-script)
    - [4 fps script](#4-fps-script)
  - [Gauss scripts](#4-gauss-scripts)
    - [180° Gauss boost](#180-gauss-boost)
    - [Slowgauss script](#slowgauss-script)
    - [Gauss script switcher](#gauss-script-switcher)
  - [Object boost scripts](#5-object-boost-scripts)
- [Anomalous Materials](#b-anomalous-materials)
  - [Testchamber scripts](#7-testchamber-scripts)
    - [Testchamber B](#test-chamber-b)
    - [Testchamber D](#test-chamber-d)
    - [Testchamber D v2](#test-chamber-d-v2)
    - [Testchamber N](#test-chamber-n)
- [Blast Pit](#c-blast-pit)
- [Power Up](#d-power-up)


## A. **Basic scripts**
### 1. Usespam script
```
alias +usespam "alias _zspecial @use;@use1"
alias -usespam "alias _zspecial;-use"
alias @use1 "+use;alias @use @use2;bxt_append _zspecial"
alias @use2 "w;alias @use @use3;bxt_append _zspecial"
alias @use3 "-use;alias @use @use4;bxt_append _zspecial"
alias @use4 "w;alias @use @use1;bxt_append _zspecial"
```
Example: `bind key +usespam`


### 2. Duckroll (aka Duckspam) Script
*Only use this one for waterboosts, `+bxt_tas_ducktap` is much better for movement purposes*
```
alias +duckroll "alias _zspecial @duck;@dr1"
alias -duckroll "alias _zspecial;-duck"
alias @dr1 "+duck;alias @duck @dr2;bxt_append _zspecial"
alias @dr2 "w;alias @duck @dr3;bxt_append _zspecial"
alias @dr3 "-duck;alias @duck @dr4;bxt_append _zspecial"
alias @dr4 "w;alias @duck @dr1;bxt_append _zspecial"
```
Example: `bind key +duckroll`

### 3. Fps scripts
#### Hold script
*If you want other value, just change the first fps value (20 fps on here) and replace `20` with something else in all the aliases (`fps_20`, `+/-fps_20_hold`, `fps_20_reset`)*
```
alias fps_20 "fps_max 20"
alias fps_default "fps_max 100"

alias +fps_20_hold "fps_20; alias -fps_20_hold fps_20_reset"
alias fps_20_reset "fps_default; alias -fps_20_hold"
```
Example: `bind key +fps_20_hold`
#### Toggle script
```
alias fps_20_toggle fps_20_toggle1
alias fps_20_toggle1 "fps_max 20; alias fps_20_toggle fps_20_toggle2"
alias fps_20_toggle2 "fps_max 100; alias fps_20_toggle fps_20_toggle1" 
```
Example: `bind key fps_20_toggle`
#### 4 fps script
```
alias 4fpsbind "fps_max 4; w; fps_max 100"
```
Example: `bind key 4fpsbind`
### 4. Gauss scripts
#### 180° Gauss boost
```
alias _taubo
alias _taubofunc "cl_pitchup 180;cl_pitchdown -180;-attack2;wait;cl_pitchup -12;cl_pitchdown 12;wait;cl_pitchup 89;cl_pitchdown 89"
alias +tau "+attack2; alias _taubo _taubofunc"
alias -tau "_taubo; alias _taubo"
```
Example: `bind key +tau`
#### Slowgauss script
```
alias tauslow "cl_pitchup 180;cl_pitchdown -180;-attack;w 50;cl_pitchup 89;cl_pitchdown 89;force_centerview"
```
Example: `bind key tauslow`
#### Gauss script switcher
```
alias tauswitch tauswitch1
alias tauswitch1 "bind mouse2 +tau; say gaussboost_ON; alias tauswitch tauswitch2"
alias tauswitch2 "bind mouse2 +attack2; say gaussboost_OFF; alias tauswitch tauswitch1"
```
Example: `bind key tauswitch`
### 5. Object Boost Scripts
#### 2000 UPS
```
alias obbo2000 "+use;w 11;-use;+jump;w;-jump"
```
Example: `bind key obbo200`

#### 1600 UPS
```
alias obbo1600 "+use;w 10;-use;+jump;w;-jump"
```
Example: `bind key obbo1600`

#### 1300 UPS
```
alias obbo1300 "+use;w 9;-use;+jump;w;-jump"
```
Example: `bind key obbo1300`

#### 1000 UPS
```
alias obbo1000 "+use;w 8;-use;+jump;w;-jump"
```
Example: `bind key obbo1000`

#### 800 UPS
```
alias obbo800 "+use;w 7;-use;+jump;w;-jump"
```
Example: `bind key obbo800`

#### Forward Object Boost (~1300-1400 UPS)
```
alias obboshoot "+use;w 10;-use;+attack2;+jump;w;-attack2;-jump"
```
Example: `bind key obboshoot`



### 6. Wait Table (BunnyModXT has its own wait table built on it, but some old scripts uses this wait table so you might need them. Just put this at the very bottom of your config.)
<details>
  <summary>📜Expand the list of aliases📜</summary>
  
  ```
alias	"w"			  "wait"
alias	"w1"			"wait"
alias	"w2"			"w;w"
alias	"w3"			"w2;w"
alias	"w4"			"w2;w2"
alias	"w5"			"w4;w"
alias	"w6"			"w3;w3"
alias	"w7"			"w6;w"
alias	"w8"			"w4;w4"
alias	"w9"			"w7;w2"
alias	"w10"			"w5;w5"
alias	"w11"			"w9;w2"
alias	"w12"			"w6;w6"
alias	"w13"			"w9;w4"
alias	"w14"			"w9;w5"
alias	"w15"			"w9;w6"
alias	"w16"			"w9;w7"
alias	"w17"			"w9;w8"
alias	"w18"			"w9;w9"
alias	"w19"			"w9;w10"
alias	"w20"			"w9;w11"
alias	"w21"			"w9;w12"
alias	"w22"			"w9;w13"
alias	"w23"			"w9;w14"
alias	"w24"			"w9;w15"
alias	"w25"			"w9;w16"
alias	"w26"			"w9;w17"
alias	"w27"			"w9;w18"
alias	"w28"			"w9;w19"
alias	"w29"			"w9;w20"
alias	"w30"			"w9;w21"
alias	"w31"			"w9;w22"
alias	"w32"			"w9;w23"
alias	"w33"			"w9;w24"
alias	"w34"			"w9;w25"
alias	"w35"			"w9;w26"
alias	"w36"			"w9;w27"
alias	"w37"			"w9;w28"
alias	"w38"			"w9;w29"
alias	"w39"			"w9;w30"
alias	"w40"			"w9;w31"
alias	"w41"			"w9;w32"
alias	"w42"			"w9;w33"
alias	"w43"			"w9;w34"
alias	"w44"			"w9;w35"
alias	"w45"			"w9;w36"
alias	"w46"			"w9;w37"
alias	"w47"			"w9;w38"
alias	"w48"			"w9;w39"
alias	"w49"			"w9;w40"
alias	"w50"			"w9;w41"
alias	"w51"			"w50;w1"
alias	"w52"			"w50;w2"
alias	"w53"			"w50;w3"
alias	"w54"			"w50;w4"
alias	"w55"			"w50;w5"
alias	"w56"			"w50;w6"
alias	"w57"			"w50;w7"
alias	"w58"			"w50;w8"
alias	"w59"			"w50;w9"
alias	"w60"			"w50;w10"
alias	"w61"			"w50;w11"
alias	"w62"			"w50;w12"
alias	"w63"			"w50;w13"
alias	"w64"			"w50;w14"
alias	"w65"			"w50;w15"
alias	"w66"			"w50;w16"
alias	"w67"			"w50;w17"
alias	"w68"			"w50;w18"
alias	"w69"			"w50;w19"
alias	"w70"			"w50;w20"
alias	"w71"			"w50;w21"
alias	"w72"			"w50;w22"
alias	"w73"			"w50;w23"
alias	"w74"			"w50;w24"
alias	"w75"			"w50;w25"
alias	"w76"			"w50;w26"
alias	"w77"			"w50;w27"
alias	"w78"			"w50;w28"
alias	"w79"			"w50;w29"
alias	"w80"			"w50;w30"
alias	"w81"			"w50;w31"
alias	"w82"			"w50;w32"
alias	"w83"			"w50;w33"
alias	"w84"			"w50;w34"
alias	"w85"			"w50;w35"
alias	"w86"			"w50;w36"
alias	"w87"			"w50;w37"
alias	"w88"			"w50;w38"
alias	"w89"			"w50;w39"
alias	"w90"			"w50;w40"
alias	"w91"			"w50;w41"
alias	"w92"			"w50;w42"
alias	"w93"			"w50;w43"
alias	"w94"			"w50;w44"
alias	"w95"			"w50;w45"
alias	"w96"			"w50;w46"
alias	"w97"			"w50;w47"
alias	"w98"			"w50;w48"
alias	"w99"			"w50;w49"
alias	"w100"		"w50;w50"
alias "w200" 		"w100;w100"
alias "w300" 		"w200;w100"
alias "w350" 		"w300;w50"
alias "w400" 		"w200;w200"
alias "w500"		"w400;w100"
alias	"w600"		"w300;w300"
alias	"w700"		"w600;w100"
alias	"w800"		"w400;w400"
```
</details>

## **B. Anomalous Materials**

### 7. Testchamber Scripts
\*troubleshooting, some common info\*\
**📝You need to execute the config with the script (`bind key "exec tc.cfg`, for example) or press the `testchamber_reset` bind (`-` by default) before doing _any_ attempt📝**


#### Test Chamber B
*The most consistent version, but it's slower by 0.7s. Only do this one if you can't get anything else to work*
<details>
  <summary>📜Click here to view the script📜</summary>
  
```
alias testchamber "tc1"
alias tmove 
alias testchamber_reset "alias testchamber tc1; alias tmove; say tc_script_reset"

alias tc1 "w 160;alias testchamber tc2; alias tmove +back" //0+9
alias tc2 "alias testchamber tc3; alias tmove +moveright" //0+9
alias tc3 "w 30;+use;w 4;-use;w 40;-moveright;-back;w 100;alias testchamber tc4; alias tmove +left" //0+9
alias tc4 "w 6;-left;w;alias testchamber tc5; alias tmove +moveright" //0+9
alias tc5 "w 22;+use;w 11;-use;+duck;w;-duck;-moveright;w 40;alias testchamber tc6; alias tmove +back" //0+9
alias tc6 "w 13;-back;alias testchamber; alias tmove" //0

bind 0 testchamber
bind 9 tmove
bind - testchamber_reset
```
</details>

<details>
  <summary>📋Usage📋</summary>
  
- Angles:
  - Pitch: **30.0 - 40.0**
  - Yaw: **125.05 - 125.09**
- Activation timing:
  - right after the cage starts going down
- Keypresses:
  - **0 90 90 90 90 90** (0 and 9+0 five times)
- Additional actions:
  - turn to the left after the script is done (after you hit the wall), so you hit the trigger and land on the reactor
  - (optional, but very recommended) do the jumpbug at `23` or `30.3` fps. Use the bxt_tas_jumpbug bind for this: `bind key +bxt_tas_jumpbug`
</details>
[Video link](https://youtu.be/-R4quekIkF4)

#### Test Chamber D
*Made by [Parklez](https://github.com/parklez). Might be inconsistent sometimes because of fps drops*
<details>
  <summary>📜Click here to view the script📜</summary>
  
```
alias testchamber "tc1"
alias move "+moveright"
alias testchamber_reset "alias testchamber tc1; alias move; say tc_script_reset"

alias tc1 "w 160;alias testchamber tc2;alias move +moveright" //0+9
alias tc2 "alias testchamber tc3;alias move +back" //0+9
alias tc3 "w 30;+use;wait;-moveright;wait;wait;wait;-use;alias testchamber tc4;alias move +moveright" //0+9
alias tc4 "w 70;cl_pitchup -89;+use;w 10;wait;wait;wait;wait;-use;cl_pitchup 89;-moveright;-back;cl_pitchdown 30;w 50;+use;alias testchamber tc5" //0+9
alias tc5 "w 10;wait;wait;wait;wait;-use;w 10;-moveright;w 30;cl_pitchdown 89;alias testchamber tc6;alias move +forward" //0+9
alias tc6 "cl_pitchdown 180;cl_pitchup -170;w 9;cl_pitchup 89;cl_pitchdown 40;wait;cl_pitchdown 89;-forward;w 63;alias testchamber tc7;alias move +moveleft" //0+9
alias tc7 "alias testchamber tc8;alias move +left" //0+9
alias tc8 "w 50;-moveleft;w 100;-left;fps_max 40;w 11;fps_max 100;alias testchamber tc9;alias move +forward" //0+9
alias tc9 "w 40; -forward; alias testchamber; alias move" //0


bind 9 move
bind 0 testchamber 
bind - testchamber_reset
```
</details>

<details>
  <summary>📋Usage📋</summary>
- Angles:
  - Pitch: **30.0 - 40.0**
  - Yaw: **136.45 - 136.51** (I personally recommend .50-.51, but doesn't really matter)
- Activation timing:
  - right after the cage starts going down
- Keypresses:
  - **0 90 90 90 90 90 90 90** (0 and 9+0 seven times), wait until you start turning mid-air (after you hit the trigger), then press **90** again and hold **A+CTRL**
</details>
[Video link](https://youtu.be/7QxRBDo6F8E)

#### Test Chamber D v2
*The fastest one. The original version was created by [Parklez](https://github.com/parklez), this one (modified by javac_) also 4fpses the trigger. Thanks to Razzie for the idea*
<details>
  <summary>📜Click here to view the script📜</summary>
  
```
alias testchamber "tc1"
alias move "+moveright"
alias testchamber_reset "alias testchamber tc1; alias move; say tc_script_reset"

alias tc1 "w 160;alias testchamber tc2;alias move +moveright" //0+9
alias tc2 "alias testchamber tc3;alias move +back" //0+9
alias tc3 "w 30;+use;wait;-moveright;wait;wait;wait;-use;alias testchamber tc4;alias move +moveright" //0+9
alias tc4 "w 70;cl_pitchup -89;+use;w 10;wait;wait;wait;wait;-use;cl_pitchup 89;-moveright;-back;cl_pitchdown 30;w 50;+use;alias testchamber tc5" //0+9
alias tc5 "w 10;wait;wait;wait;wait;-use;w 10;-moveright;w 30;cl_pitchdown 89;alias testchamber tc6;alias move +forward" //0+9
alias tc6 "cl_pitchdown 180;cl_pitchup -170;w 9;cl_pitchup 89;cl_pitchdown 40;wait;cl_pitchdown 89;-forward;w 63;alias testchamber tc7;alias move +moveleft" //0+9
alias tc7 "alias testchamber tc8;alias move +left" //0+9
alias tc8 "w 50;-moveleft;w 100;-left;fps_max 40;w 11;fps_max 100;alias testchamber tc9;alias move +forward" //0+9
alias tc9 "w 40; -forward; alias move +moveleft; alias testchamber tc10" //0+9
alias tc10 "+duck; w 85; -duck; alias move +left; alias testchamber tc11" //0+9
alias tc11 "w 30; fps_max 4; w; fps_max 100; w 5; -moveleft; -left; alias testchamber; alias move" //0


bind 9 move
bind 0 testchamber 
bind - testchamber_reset
```
</details>

<details>
  <summary>📋Usage📋</summary>
- Angles:
  - Pitch: **30.0 - 40.0**
  - Yaw: **136.45 - 136.51** (I personally recommend .50-.51, but doesn't really matter)
- Activation timing:
  - right after the cage starts going down
- Keypresses:
  - **0 90 90 90 90 90 90 90** (**0** and **9+0** seven times), wait until you start turning mid-air (after you hit the trigger), then press **90 90 90**
</details>
[Video link](https://youtu.be/mnLNYTiTWYs)

#### Test Chamber N
*Made by N4Rk0t1k. The best one in terms of speed/consistency ratio. Try this one if you have any fps issues and can't do the TC_D vesion. Slower by 0.2-0.3s*
<details>
  <summary>📜Click here to view the script📜</summary>
  
```
alias cart preboost1
alias pausespam "w; unpause; w; setpause"
alias longpausespam "pausespam; pausespam; pausespam; pausespam; pausespam; pausespam; pausespam"
alias testchamber_reset "alias cart preboost1; alias mcart; say tc_script_reset"

alias preboost1             "pausable 1; w 5; fps_max 18; w 34; alias cart preboost2; alias mcart +moveright" //0+9
alias preboost2             "+use; w 2; -use; w 12; -moveright; alias cart preboost3; alias mcart +left" //0+9
alias preboost3             "w 5; +use; w 1; -left; w 1; -use; -left; fps_max 99; w 2; alias cart cartboost; alias mcart +moveright" //0+9
alias cartboost             "w 33; +use; w 3; setpause; longpausespam; unpause; -use; w 13; fps_max 30; w 9; alias cart cartfly; alias mcart +right" //0+9
alias cartfly               "w 5; -moveright; -right; alias cart cartlanding1; alias mcart +moveleft" //0+9
alias cartlanding1          "alias mcart +left; alias cart cartlanding2" //0+9
alias cartlanding2          "speak scientist/scream20; fps_max 28.7; w 16; -moveleft; w 44; -left; +bxt_tas_jumpbug; fps_max 10; w 4; -bxt_tas_jumpbug; fps_max 100; alias cart cartwindow; alias mcart +moveright" //0+9
alias cartwindow            "w 30; -moveright; alias cart; alias mcart" //0


bind 0 cart
bind 9 mcart
bind - testchamber_reset
```
</details>

<details>
  <summary>📋Usage📋</summary>
- Angles:
  - Pitch: **30.0 - 40.0**
  - Yaw: **73.00 - 73.10** (I personally recommend .05 - 0.7, but doesn't really matter)
- Activation timing:
  - right after the cage starts going down
- Keypresses:
  - (first option) **0 90 90 90 90 90 90** (**0** and **9+0** six times), wait until you hear the scientist screaming, then press **9+0** again and hold **W+CTRL**
  - (second option) **0 90 90 90 90 90 90 90** (**0** and **9+0** seven times), start holding **W+CTRL** before landing
- Tips:
  - Tapping **D** after the level changes helps with landing a lot
</details>
[Video link](https://youtu.be/DnRJmZiLDFM)

## **C. Blast Pit**

### 8. Jumpbugs
<details>
  <summary>Click Here To View Scripts</summary>
  
#### jb1 (First Elevator)
```
alias fps_90 "fps_max 90.90909"
alias fps_100 "fps_max 100"
alias +bpjb1 "fps_90; w5; +bxt_tas_jumpbug" 
alias -bpjb1 "-bxt_tas_jumpbug; fps_100"
```
Example: `bind y +bpjb1`

#### jb2 (Second Elevator)
```
alias fps_55 "fps_max 55.55555"
alias fps_100 "fps_max 100"
alias +bpjb2 "fps_55; w20; +bxt_tas_jumpbug" 
alias -bpjb2 "-bxt_tas_jumpbug; fps_100"
```
Example: `bind y +bpjb2`

#### jb3 (Pipe Before Power Up)
```
alias fps_33 "fps_max 58.82353"
alias +bpjb3 "fps_33; w 5; +bxt_tas_jumpbug" 
alias -bpjb3 "-bxt_tas_jumpbug; fps_100"
```
Example: `bind y +bpjb3`
</details>

### 9. Nade Boost Scripts

#### Maxam's Nade Route
```
alias bp_nade2 "cl_pitchdown 30;cl_pitchup -30;+duck;+jump;wait;-attack;w 15;-jump;-duck;cl_pitchup 89;cl_pitchdown 89;force_centerview; say fps_90"
```
Example: `bind tab "bp_nade2"`
#### Maxam's Nade Route(From The Slop Version)
(This one is pretty much harder, its recommended to use it only if you have low hp)
```
alias bp_nade3 "cl_pitchdown 89; cl_pitchup -89; -attack; w; cl_pitchup 89; force_centerview"
```
Example: `bind tab "bp_nade3"`



#### Tentacle Room Boost 
```
alias bpbutton2 "+attack2; -jump; w; weapon_handgrenade;-attack2; -moveleft; -moveright; weapon_handgrenade; w 20; cl_pitchdown 45; cl_pitchup -45; w 40; -duck; w 30; +use; w 20; -use; w 15; +jump; w; +duck; cl_pitchdown 89; cl_pitchup 89; fps_max 7.5; w 2; -jump; fps_max 100; w 50; -duck"
```
Example: `bind g "bpbutton2"`

### 10. Hl21 Box Script
```
alias box1 "fps_max 100; w 100; alias move +left; alias box box2" //k
alias box2 "w 3; -left; alias move +moveright; alias box box3" //l + k
alias box3 "w 22; +use; w 9; -use; w 20; +use; w 6; -use; +duck; w; -duck; w; +duck; +use; w 21; -use; -duck; w 15; +use; w 8; -use; w; +duck; w 25; -duck; w 25; +use; w 6; -use; alias move +forward; alias box box4" //l + k
alias box4 "w 23; +use; w 10; -use; w 5; +use; w 8; -use; w 25; -moveright; w 10; +use; w 4; -use; w 42; -forward; w 30; alias move +moveleft; alias box box5" //l + k
alias box5 "w 10; +use; w 9; -use; -moveleft; alias move +right; alias box box6" //l + k
alias box6 "w 12; -right; w 53; record bp1; alias move +moveleft; alias box box7" //l + k
alias box7 "w 5; alias move +forward; alias box box8" //l + k
alias box8 "w 7; -forward; w 25; -moveleft; w 5; alias move +forward; alias box box9" //l + k
alias box9 "w 2; +use; w 11; +duck; w; -duck; w; -use; alias move +moveright; alias box box10" //l + k
alias box10 "alias move +right; alias box box11" //l + k
alias box11 "w 4; -right; -moveright; -forward; weapon_shotgun; alias move; alias box" //l + k

alias box box1
alias move
```
#### Usage:
* bind "k" box
* bind "l" move
* You need to re-execute the config with the script after each attempt
* Push the box into the corner and stand close to it and the wall.
* Pitch doesn't matter much, just aim at the corner of the box 
* (make sure you don't aim too high tho otherwise it might not push the box in middle of script).
* yaw: 262.41 - 262.70
* Press K LK LK LK LK LK LK LK LK LK LK (K once and LK 10 times).
* Hold space and make a strafe to the right after changelevel.
* You have to press the buttons fast enough. You can press more than 10 times as well it will still work.
* You can change the number of waits in alias box1 (every 100 waits = 1 second) if you don't have enough time to press the buttons.

## **D. Power Up**
  
### 11. Changelevel Delay Scripts
<details>
  <summary>Click Here To View Scripts</summary>

#### PU CLD (A)
```
alias puskip "-jump;-moveright;-moveleft;speak fvox/power_level_is;w 100;speak fvox/beep;w 100;speak fvox/beep;w 100;speak fvox/beep;w 100;speak fvox/beep;w 100;speak fvox/beep;w 100;speak fvox/beep;cl_pitchdown 180;cl_pitchup -179;w 30;cl_pitchup -30;cl_pitchdown 31;wait;cl_pitchup 89;cl_pitchdown 89;w 10;+use;w 11;-use;+jump;wait;-jump"
```
Video guide: [link](https://www.youtube.com/watch?v=IkZ4wWKrLVg)\
Example: `bind g puskip`

#### Power Up B
*Facing forward, no object boost.*
```
alias puskip "speak fvox/power_level_is;w 100;speak fvox/beep;w 100;speak fvox/beep;w 100;speak fvox/beep;w 100;speak fvox/beep;w 100;speak fvox/beep;w 50"
```
Example: `bind g puskip`
How to use: Walk forward and activate the script as you walk across the level change trigger, grab the tripmines and wait against the wall.


#### PU CLD (C) [Faster One, has less delay)
*Facing forward, with object boost!*
```
alias puskip "weapon_shotgun;-jump;-moveright;-moveleft;w 280;+use;w 8;-use;+jump;wait;-jump;+attack2;wait;-attack2;+duck;w 27;-duck"
```
Example: `bind g puskip`

#### PU CLD (C) [Slower One, has more delay]
*Facing forward, with object boost!*
```
alias puskip "weapon_shotgun;-jump;-moveright;-moveleft;w 350;+use;w 12;-use;+jump;wait;-jump;+attack2;wait;-attack2;+duck;w 28;-duck"
```
Example: `bind g puskip`

Video guide: [link](https://clips.twitch.tv/PuzzledTangentialClipsdadRickroll)
</details>





