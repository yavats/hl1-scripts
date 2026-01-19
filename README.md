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
    - [Testchamber B](#-testchamber-b)
    - [Testchamber N](#-testchamber-n)
    - [Testchamber D](#-testchamber-d)
    - [Testchamber D v2](#-testchamber-d-v2)
- [Unforeseen Consequences](c-unforeseen-consequences)
  - [Object Boost Script](#8-object-boost-script)
- [Office Complex](#d-office-complex)
  - [Object Boost Script](#9-object-boost-script)
- [Blast Pit](#e-blast-pit)
  - [Jumpbug Scripts](#10-jumpbugs)
  - [Nade Boost Scripts](#11-nade-boost-scripts)
  - [Hl21 Box Script](#12-hl21-box-script)
- [Power Up](#f-power-up)
  - [ChangeLevel Delay Scripts](#13-changelevel-delay-scripts)
- [On A Rail](#g-on-a-rail)
  - [Jumpbug Scripts](#14-jumpbugs)
  - [Object Boost Script](#15-object-boost-script-forward)
- [Apprehension](#h-apprehension)
  - [Object Boost Script](#16-object-boost-script-bridge)
- [Residue Processing](#j-residue-processing)
  - [Meatgrab Script](#17-meatgrab-script)
  - [RPClip Script](#18-rpclip-script)
- [Surface Tension](#k-surface-tension)
  - [CLD Scripts](#19-cld-scripts)
  - [P2P Scripts](#20-hl21-p2p-scripts)
  - [Slowgauss Script](#21-slowgauss-after-ihd-door)
  - [Nadeboost](#22-nadeboost-for-new-st-route)
- [Forget About Freeman](#l-forget-about-freeman)
  - [Chairboost Script](#23-chairboost-script)
  - [CLD Scripts](#24-cld-scripts)
- [Lambda Core](#m-lambda-core)
  - [Watergauss Clip Script](#25-watergauss-clip-script)
  - [Smg Boost Scripts](#26-smg-boost-scripts)
- [Xen](#n-xen)
  - [Jumpbug + Viewangle](#27-jumpbugs)

  
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
Example: `bind key +usespam`\
Usage: hold the script key


### 2. Duckroll (aka Duckspam) script
*Only use this for waterboosts, `+bxt_tas_ducktap` is much better for movement purposes*
```
alias +duckroll "alias _zspecial @duck;@dr1"
alias -duckroll "alias _zspecial;-duck"
alias @dr1 "+duck;alias @duck @dr2;bxt_append _zspecial"
alias @dr2 "w;alias @duck @dr3;bxt_append _zspecial"
alias @dr3 "-duck;alias @duck @dr4;bxt_append _zspecial"
alias @dr4 "w;alias @duck @dr1;bxt_append _zspecial"
```
Example: `bind key +duckroll`\
Usage: hold the script key


### 3. Fps scripts
#### Hold script
*If you want another value, replace `20` in the `fps_max 20` command and alias names (`+/-fps_20_hold`, `fps_20_reset`)*
```
alias +fps_20_hold "fps_max 20; alias -fps_20_hold fps_20_reset"
alias fps_20_reset "fps_max 100; alias -fps_20_hold"
```
Example: `bind key +fps_20_hold`\
Usage: hold the script key to lower fps, release to change back to default
#### Toggle script
```
alias fps_20_toggle fps_20_toggle1
alias fps_20_toggle1 "fps_max 20; alias fps_20_toggle fps_20_toggle2"
alias fps_20_toggle2 "fps_max 100; alias fps_20_toggle fps_20_toggle1" 
```
Example: `bind key fps_20_toggle`\
Usage: press the script key to lower fps, press again to change back to default
#### 4 fps script
```
alias 4fpsbind "fps_max 4; w; fps_max 100"
```
Example: `bind key 4fpsbind`\
Usage: press the script key once


### 4. Gauss scripts
#### 180° Gauss boost
```
alias _taubo
alias _taubofunc "cl_pitchup 180;cl_pitchdown -180;-attack2;wait;cl_pitchup -12;cl_pitchdown 12;wait;cl_pitchup 89;cl_pitchdown 89"
alias +tau "+attack2; alias _taubo _taubofunc"
alias -tau "_taubo; alias _taubo"
```
Example: `bind key +tau`\
Usage: hold the script key to charge, release to boost
#### Alternative gauss boost func (c4a1d Interloper selfgauss)
```
alias _taubofunc2 "cl_pitchup 165;cl_pitchdown -165;-attack2;w;cl_pitchup 89;cl_pitchdown 89;force_centerview"
```
Example: `bind key "alias _taubofunc _taubofunc2"`\
Usage: either use a bind for `alias _taubofunc _taubofunc2` to change the `+tau` script behaviour or duplicate it, rename and make a rebind (`bind key "bind mouse2 +tau2"`, for example)\
[Video link](https://youtu.be/EJgwb4_xUXU)\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/taubofunc2.sav)
#### Slowgauss script
```
alias slowgauss "cl_pitchup 180;cl_pitchdown -180;-attack;w 50;cl_pitchup 89;cl_pitchdown 89;force_centerview"
```
Example: `bind key slowgauss`\
Usage: start charging with `mouse2`, immediately switch to `mouse1`, wait around 3s for the gauss to be fully charged and press the script key to boost. Note that the script has a 0.5s delay to make sure the shot happens (necessary due to shooting being cycle-based). Also you need to have exactly 1 or 2 ammo for this trick to work.\
[Video link](https://youtu.be/d7jesoiDjr4)\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/slowgauss.sav)
#### Gauss script switcher
```
alias tauswitch tauswitch1
alias tauswitch1 "bind mouse2 +tau; say gaussboost_ON; alias tauswitch tauswitch2"
alias tauswitch2 "bind mouse2 +attack2; say gaussboost_OFF; alias tauswitch tauswitch1"
```
Example: `bind key tauswitch`\
Usage: press the script key to change the `mouse2` bind to `+tau`, press again to revert the default bind (`+attack2`) back


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
#### Forward boost (~1300-1400 UPS)
```
alias obboshoot "+use;w 10;-use;+attack2;+jump;w;-attack2;-jump"
```
Example: `bind key obboshoot`


### 6. Wait table
*Bunnymod XT has its own built-in `w value` function, but you might still need the table below for some old scripts to work without rewriting them*
<details>
  <summary>📜Expand the table📜</summary>
  
  ```
alias "w"       "wait"
alias "w1"      "wait"
alias "w2"      "w;w"
alias "w3"      "w2;w"
alias "w4"      "w2;w2"
alias "w5"      "w4;w"
alias "w6"      "w3;w3"
alias "w7"      "w6;w"
alias "w8"      "w4;w4"
alias "w9"      "w7;w2"
alias "w10"     "w5;w5"
alias "w11"     "w9;w2"
alias "w12"     "w6;w6"
alias "w13"     "w9;w4"
alias "w14"     "w9;w5"
alias "w15"     "w9;w6"
alias "w16"     "w9;w7"
alias "w17"     "w9;w8"
alias "w18"     "w9;w9"
alias "w19"     "w9;w10"
alias "w20"     "w9;w11"
alias "w21"     "w9;w12"
alias "w22"     "w9;w13"
alias "w23"     "w9;w14"
alias "w24"     "w9;w15"
alias "w25"     "w9;w16"
alias "w26"     "w9;w17"
alias "w27"     "w9;w18"
alias "w28"     "w9;w19"
alias "w29"     "w9;w20"
alias "w30"     "w9;w21"
alias "w31"     "w9;w22"
alias "w32"     "w9;w23"
alias "w33"     "w9;w24"
alias "w34"     "w9;w25"
alias "w35"     "w9;w26"
alias "w36"     "w9;w27"
alias "w37"     "w9;w28"
alias "w38"     "w9;w29"
alias "w39"     "w9;w30"
alias "w40"     "w9;w31"
alias "w41"     "w9;w32"
alias "w42"     "w9;w33"
alias "w43"     "w9;w34"
alias "w44"     "w9;w35"
alias "w45"     "w9;w36"
alias "w46"     "w9;w37"
alias "w47"     "w9;w38"
alias "w48"     "w9;w39"
alias "w49"     "w9;w40"
alias "w50"     "w9;w41"
alias "w51"     "w50;w1"
alias "w52"     "w50;w2"
alias "w53"     "w50;w3"
alias "w54"     "w50;w4"
alias "w55"     "w50;w5"
alias "w56"     "w50;w6"
alias "w57"     "w50;w7"
alias "w58"     "w50;w8"
alias "w59"     "w50;w9"
alias "w60"     "w50;w10"
alias "w61"     "w50;w11"
alias "w62"     "w50;w12"
alias "w63"     "w50;w13"
alias "w64"     "w50;w14"
alias "w65"     "w50;w15"
alias "w66"     "w50;w16"
alias "w67"     "w50;w17"
alias "w68"     "w50;w18"
alias "w69"     "w50;w19"
alias "w70"     "w50;w20"
alias "w71"     "w50;w21"
alias "w72"     "w50;w22"
alias "w73"     "w50;w23"
alias "w74"     "w50;w24"
alias "w75"     "w50;w25"
alias "w76"     "w50;w26"
alias "w77"     "w50;w27"
alias "w78"     "w50;w28"
alias "w79"     "w50;w29"
alias "w80"     "w50;w30"
alias "w81"     "w50;w31"
alias "w82"     "w50;w32"
alias "w83"     "w50;w33"
alias "w84"     "w50;w34"
alias "w85"     "w50;w35"
alias "w86"     "w50;w36"
alias "w87"     "w50;w37"
alias "w88"     "w50;w38"
alias "w89"     "w50;w39"
alias "w90"     "w50;w40"
alias "w91"     "w50;w41"
alias "w92"     "w50;w42"
alias "w93"     "w50;w43"
alias "w94"     "w50;w44"
alias "w95"     "w50;w45"
alias "w96"     "w50;w46"
alias "w97"     "w50;w47"
alias "w98"     "w50;w48"
alias "w99"     "w50;w49"
alias "w100"    "w50;w50"
alias "w200"    "w100;w100"
alias "w300"    "w200;w100"
alias "w350"    "w300;w50"
alias "w400"    "w200;w200"
alias "w500"    "w400;w100"
alias "w600"    "w300;w300"
alias "w700"    "w600;w100"
alias "w800"    "w400;w400"
```
</details>



## **B. Anomalous Materials**

### 7. Elevator reverse scripts
#### 🔴 Elevator reverse script v1
*Made by javac_*
- Less consistent than [v2](#-elevator-reverse-script-v2)
- Faster by 0.1-0.2s
- Sometimes doesn't work even if everything was done correctly, probably has something to do with the elevator button cycles (?)

<details>
  <summary>📜Click here to view the script📜</summary>
  
```
// part 1
alias wolk1 "fps_max 100; w 50; alias wolk wolk2; alias wolkmove +moveright"
alias wolk2 "w 8; +speed; w 17; -speed; -moveright; alias wolkmove; alias wolk" 

alias wolk wolk1
alias wolkmove


// part 2
alias elev1 "fps_max 100; w 93; alias elevmove +forward; alias elev elev2" // 3
alias elev2 "force_centerview; fps_max 4; w; fps_max 100; w 10; +duck; alias elevmove +moveright; alias elev elev3" // 1 3
alias elev3 "w 29; -moveright; -forward; w 20; alias elevmove +left; alias elev elev4" // 1 3
alias elev4 "w 10; alias elevmove +forward; alias elev elev5" // 1 3
alias elev5 "+use; w; -use; w 12; -left; w 80; alias elevmove +moveright; alias elev elev6" // 1 3
alias elev6 "alias elevmove +right; alias elev elev7" // 1 3
alias elev7 "w 10; fps_max 4; w; fps_max 100; w; -forward; -duck; fps_max 4; w; fps_max 100; w 2; -moveright; -right; alias elev; alias elevmove" // 1 3

alias elev elev1
alias elevmove



// binds
bind 2 wolk
bind 4 wolkmove
bind 3 elev
bind 1 elevmove
```
</details>

<details>
  <summary>📋Usage📋</summary>

Go into the left corner, set the angles and activate the first part of the script. Wait until the elevator reaches the highest point and activate the second part.

- **Angles:**
  - Pitch: doesn't matter
  - Yaw: `89.9 - 91.0`
- **Activation timing:**
  - 1st part: any moment after pressing the elevator button
  - 2nd part: right after the elevator reaches its highest position
- **Keypresses**:
  - 1st part: `2 4 2`
  - 2nd part: `3 13 13 13 13 13 13` (`3` and then `13` six times)
</details>

[Video link](https://youtu.be/g3vjjVVva70)\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/elevator_reverse.sav)




#### 🟡 Elevator reverse script v2
*Made by N4rk0t1k*
- Way more consistent than [v1](#-elevator-reverse-script-v1) due to the fixed activation timing
- Slightly slower
- Still has the same button cycle timing issue as [v1](#-elevator-reverse-script-v1)
<details>
  <summary>📜Click here to view the script📜</summary>
  
```
alias amel_use "cl_pitchup 30; cl_pitchdown -30; +use; w; -use; cl_pitchup 0; w; cl_pitchup 89; cl_pitchdown 89"
alias amel_fps "fps_max 4; w; fps_max 40"
alias pre_amel "fps_max 20; -back; -moveright; -moveleft; -jump; -duck; +use; w; -use; w 50; -forward; w 23; fps_max 38; w 28; alias AMEL amel1"

alias amel1 "sensitivity 0; alias AMEL amel2; alias AMEL_MOVE +moveright" // 3
alias amel2 "w 8; -moveright; +use; w 6; -use; amel_fps; alias AMEL amel3; alias AMEL_MOVE +forward" // 1 3
alias amel3 "w 7; +duck; w 3; -forward; alias AMEL amel4; alias AMEL_MOVE +moveright" // 1 3
alias amel4 "w 10; alias AMEL amel5; alias AMEL_MOVE +forward" // 1 3
alias amel5 "w 5; -moveright; alias AMEL amel6; alias AMEL_MOVE +moveleft" // 1 3
alias amel6 "w 4; -moveleft; amel_use; w 3; -forward; w 4; amel_fps; alias AMEL amel7; alias AMEL_MOVE +moveleft" // 1 3
alias amel7 "w 10; alias AMEL amel8; alias AMEL_MOVE +forward" // 1 3
alias amel8 "w 10; -moveleft; w; alias AMEL amel9; alias AMEL_MOVE +right" // 1 3
alias amel9 "alias AMEL amel10; alias AMEL_MOVE +moveright" // 1 3
alias amel10 "w; fps_max 4; w 2; -moveright; fps_max 40; -right; -duck; -forward; fps_max 100; amel_sens; alias AMEL; alias AMEL_MOVE" // 1 3

alias AMEL
alias AMEL_MOVE



// settings
alias amel_sens "sensitivity 3"

// binds
bind mouse2 pre_amel
bind 3 AMEL
bind 1 AMEL_MOVE
```
</details>

<details>
  <summary>📋Usage📋</summary>

Hold `w` and press the `pre_amel` key (`mouse2` here) to activate the elevator button. Go into the left corner, set the angles and press the script keys.

- **Angles:**
  - Pitch: doesn't matter
  - Yaw: `90.0 - 91.0` (~`90.5` is recommended)
- **Activation timing:**
  - none (the script starts with pressing the elevator button)
- **Keypresses**:
  - `mouse2`, `3 13 13 13 13 13 13 13 13 13` (`3` and then `13` nine times), then hold `w + d`
- **Additional actions**:
  - change sensitivity in the `amel_sens` alias to your default
</details>

[Video link](https://youtu.be/CYudVS20Zxc)\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/elevator_reverse.sav)





### 8. Test Chamber scripts
\*troubleshooting, some common info\*\
**📝You need to execute the config with the script (`bind key "exec tc.cfg`, for example) or press the `testchamber_reset` bind (`-` by default) before doing _any_ attempt📝**

#### 🟢 Testchamber B
*Made by [Parklez](https://github.com/parklez), modified by javac_*
- Semi-automated (manual window landing)
- The most consistent version
- ~1s slower than [Testchamber D](#-testchamber-d)
- Only use this one if you can't get anything else to work
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

- **Angles:**
  - Pitch: `30.0 - 40.0`
  - Yaw: `125.05 - 125.09`
- **Activation timing:**
  - right after the cage starts going down
- **Keypresses**:
  - `0 90 90 90 90 90` (`0` and then `90` five times)
- **Additional actions:**
  - turn to the left after the script is done (after you hit the wall), so you hit the trigger and land on the reactor
  - (optional, but very recommended) do the jumpbug at `23` or `30.3` fps
</details>

[Video link](https://youtu.be/-R4quekIkF4)\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/tc_b.sav)


#### 🟡 Testchamber N
*Made by N4Rk0t1k*
- Fully automated
- Very consistent even with fps drops
- 0.3s slower than [Testchamber D](#-testchamber-d)
- Try this one if you have performance issues that prevent you from using version D
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
  
- **Angles:**
  - Pitch: `30.0 - 40.0`
  - Yaw: `73.00 - 73.10` (I personally recommend .05 - 0.7, but doesn't really matter)
- **Activation timing:**
  - right after the cage starts going down
- **Keypresses:**
  - (first option) `0 90 90 90 90 90 90` (`0` and then `90` six times), wait until you hear the scientist screaming, then press `90` again and hold `w + ctrl`
  - (second option) `0 90 90 90 90 90 90 90` (`0` and `90` seven times), start holding `w + ctrl` before landing
- **Tips:**
  - Tapping `d` after the level changes helps with landing a lot
</details>

[Video link](https://youtu.be/DnRJmZiLDFM)\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/tc_n.sav)


#### 🟠 Testchamber D
*Made by [Parklez](https://github.com/parklez)*
- Fully automated
- May be inconsistent if you have performance issues
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
  
- **Angles:**
  - Pitch: `30.0 - 40.0`
  - Yaw: `136.45 - 136.51` (I personally recommend `.50` or `.51`, but doesn't really matter)
- **Activation timing:**
  - right after the cage starts going down
- **Keypresses:**
  - `0 90 90 90 90 90 90 90` (`0` and then `90` seven times), wait until you start turning mid-air (after you hit the trigger), then press `90` again and hold `a + ctrl`
</details>

[Video link](https://youtu.be/7QxRBDo6F8E)\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/tc_d.sav)


#### 🔴 Testchamber D v2
*[Testchamber D](#-testchamber-d) extended by javac_. Thanks to Razzie for the idea*
- Fully automated + extended to 4 fps the UC trigger
- 0.1s faster than [Testchamber D](#-testchamber-d)
- It's not necessary to saveload after the script
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
  
- **Angles:**
  - Pitch: `30.0 - 40.0`
  - Yaw: `136.45 - 136.51` (I personally recommend `.50 - .51`, but doesn't really matter)
- **Activation timing:**
  - right after the cage starts going down
- **Keypresses:**
  - `0 90 90 90 90 90 90 90` (`0` and then `90` seven times), wait until you start turning mid-air (after you hit the trigger), then press `90 90 90`
</details>

[Video link](https://youtu.be/mnLNYTiTWYs)\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/tc_d.sav)





## **C. Blast Pit**


### 9. Nade boost scripts

#### 💣 Barrel bridge nade
*Made by [Parklez](https://github.com/parklez)*
- Use with ≤ 9 armor
```
alias bp_nade "fps_max 100; cl_pitchdown 85;cl_pitchup -85;+duck;+jump;w;-attack;w 15;-jump;-duck;cl_pitchup 89;cl_pitchdown 89;force_centerview"
```
Example: `bind key bp_nade`\
Usage: walk forward and activate the script\
[Video link](https://youtu.be/6au7vtLFNBY)\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/bp_nade.sav)


#### 💣 Maxam's nade route boost v1
- Requirements: 51 hp, 20 armor
- Makes an autosave midair as a backup
```
alias bp_nade2 "fps_max 100; cl_pitchdown 30;cl_pitchup -30;+duck;+jump;w;-attack;w 15;-jump;-duck;cl_pitchup 89;cl_pitchdown 89;force_centerview; save autosave"
```
Example: `bind key bp_nade2`\
Usage: walk forward and activate the script\
[Video link](https://youtu.be/DkA5ik4JRn4)\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/bp_nade2.sav)


#### 💣 Maxam's nade route boost v2
- Requiremenets: 53 hp, 20 armor
- More consistent boost than [v1](#maxams-nade-route-boost-v1)
- Makes an autosave midair as a backup
```
alias bp_nade3 "fps_max 100; cl_pitchdown 15;cl_pitchup -15;+duck;+jump;w;-attack;w 15;-jump;-duck;cl_pitchup 89;cl_pitchdown 89;force_centerview; save autosave"
```
Example: `bind key bp_nade3`\
Usage: walk forward and activate the script\
[Video link](https://youtu.be/DkA5ik4JRn4) (same as [v1](#maxams-nade-route-boost-v1))\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/bp_nade2.sav)


#### 💣 Slope nade boost
- Requirements: ~30-35 hp, 20 armor
- Much more difficult execution
- Slightly faster than other scripts
```
alias bp_nade4 "fps_max 100; +jump; cl_pitchdown 89; cl_pitchup -89; -attack; w; cl_pitchup 89; force_centerview; -jump"
```
Example: `bind key bp_nade4`\
Usage: cook a nade beforehand, gain around 600 ups, land near the slope and press the script key. DON'T JUMP ON YOUR OWN, THE SCRIPT DOES IT FOR YOU! It's highly recommended to do a jumpbug before this boost to save more hp and get a good jump pattern\
[Video link](https://youtu.be/pbZzpa-TUfY)\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/bp_nade4.sav)


#### 💥 Fire button room boost v1
- Requirements: 41 hp (may vary by +-2)
- Makes an autosave in case of failure
- Harder activation timing
```
alias bpbutton "fps_max 100; +attack2; -jump; w; weapon_handgrenade;-attack2; -moveleft; -moveright; weapon_handgrenade; w 20; cl_pitchdown 45; cl_pitchup -45; w 30; save autosave; w 10; -duck; w 30; +use; w 20; -use; w 15; +jump; w; +duck; cl_pitchdown 89; cl_pitchup 89; w; -jump; w 60; -duck"
```
Example: `bind key bpbutton`\
Usage: cook a nade a couple frames after the changelevel, start jumping as soon as you touch the ground, switch to the shotgun, keep jumping and break the bottom plank BY ACTIVATING THE SCRIPT, not with regular `+attack2`. Hold `w` during activation\
[Video link](https://youtu.be/wvnJec6XsXU)\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/bpbutton.sav)


#### 💥 Fire button room boost v2
- Requirements: 45 hp (may vary by +-2)
- Makes an autosave in case of failure
- Easy activation timing -> more consistent
```
alias bpbutton2 "fps_max 100; +attack2; -jump; w; weapon_handgrenade;-attack2; -moveleft; -moveright; weapon_handgrenade; w 20; cl_pitchdown 45; cl_pitchup -45; w 30; save autosave; w 10; -duck; w 30; +use; w 20; -use; w 15; +jump; w; +duck; cl_pitchdown 89; cl_pitchup 89; fps_max 7.5; w 2; -jump; fps_max 100; w 50; -duck"
```
Example: `bind key bpbutton`\
Usage: cook a nade before the changelevel, start jumping as soon as you touch the ground, switch to the shotgun, keep jumping and break the bottom plank BY ACTIVATING THE SCRIPT, not with regular `+attack2`. Hold `w` during activation\
[Video link](https://youtu.be/_Llz6Epy7OA)\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/bpbutton.sav)





### 10. 📦 HL21 box script
*made by javac_*\
A HL21-like script, which consists of 2 parts. The first one involves a CLD and object boost, the second one makes a turn and blows up the explosive crates. It keeps all your health so you can use it for something else (for example, [this boost](#-maxams-route-nade-boost-v1) ).

<details>
  <summary>📜Click here to view the script📜</summary>

1st part (main)
```
alias box1 "save autosave; fps_max 100; cl_pitchdown 28.7; cl_pitchup -28.7; sensitivity 0; w 100; alias boxmove +left; alias box box2" // 1
alias box2 "w 3; -left; alias boxmove +moveright; alias box box3" //2+1
alias box3 "w 22; +use; w 9; -use; w 20; +use; w 6; -use; +duck; w; -duck; w; +duck; +use; w 21; -use; -duck; w 15; +use; w 8; -use; w; +duck; w 25; -duck; w 25; +use; w 6; -use; alias boxmove +forward; alias box box4" //2+1
alias box4 "w 23; +use; w 10; -use; w 5; +use; w 8; -use; w 25; -moveright; w 10; +use; w 4; -use; w 42; -forward; w 30; alias boxmove +moveleft; alias box box5" //2+1
alias box5 "w 10; +use; w 9; -use; -moveleft; alias boxmove +right; alias box box6" //2+1
alias box6 "w 12; -right; w 53; alias boxmove +moveleft; alias box box7" //2+1
alias box7 "w 5; alias boxmove +forward; alias box box8" //2+1
alias box8 "w 7; -forward; w 25; -moveleft; w 5; alias boxmove +forward; alias box box9" //2+1
alias box9 "w 2; +use; w 11; +duck; w; -duck; w; -use; alias boxmove +moveright; alias box box10" //2+1
alias box10 "alias boxmove +right; alias box box11" //2+1
alias box11 "w 4; -right; -moveright; -forward; weapon_shotgun; bpbox_sens; cl_pitchdown 89; cl_pitchup 89; alias boxmove; alias box" //2+1
alias box box1
alias boxmove

// settings
alias bpbox_sens "sensitivity 3"

// binds
bind 1 box
bind 2 boxmove
```

2nd part (extension)
```
alias af1 "sensitivity 0; alias afmove +moveright; alias af af2" // 9
alias af2 "+jump; w 34; alias afmove +right; alias af af3" // 0+9
alias af3 "w 8; -right; +duck; w 20; alias af af4" // 0+9
alias af4 "w 4; -moveright; w 32; -right; cl_pitchup -10.5; cl_pitchdown 10.5; w 20; +attack2; w 10; -attack2; w 20; -duck; -moveright; w 17; alias afmove +moveright; alias af af5" // 0+9
alias af5 "w 9; alias afmove +right; alias af af6" // 0+9
alias af6 "w 15; -right; w 50; -moveright; -jump; cl_pitchdown 89; cl_pitchup 89; alias af; alias afmove; save autosave; bpbox_sens" // 0+9
alias af af1
alias afmove

// binds
bind 9 af
bind 0 afmove
```

</details>



<details>
  <summary>📋Usage (basic version)📋</summary>

Only uses 1st part of the script
  
- **Angles:**
  - Pitch: doesn't matter much, just aim at the box corner
  - Yaw: `262.40 - 262.71`
- **Activation timing:**
  - none
- **Keypresses:**
  - `1 21 21 21 21 21 21 21 21 21 21` (`1` and then `21` ten times) before you touch the changelevel trigger
  - Start holding `d + space` before the changelevel (but not too early)
- **Additional actions:**
  - Change sensitivity in the `bpbox_sens` alias to your default
</details>

[Video link (basic ver.)](https://youtu.be/5Sl6lXTGL60)

<details>
  <summary>📋Usage (extended version)📋</summary>

Uses both parts of the script
  
- **Angles:**
  - Pitch: doesn't matter much, just aim at the box corner
  - Yaw: `262.40 - 262.62`
- **Activation timing:**
  - 1st part: none
  - 2nd part: after touching the changelevel trigger
- **Keypresses:**
  - 1st part: `1 21 21 21 21 21 21 21 21 21 21` (`1` and then `21` ten times) before you touch the changelevel trigger
  - 2nd part: `9 09 09 09 09 09` (`9` and then `09` five times) after you touch the changelevel trigger
- **Additional actions:**
  - Change sensitivity in the `bpbox_sens` alias to your default
</details>

[Video link (extended ver.)](https://youtu.be/TkOWi8z1Aa4)

<details>
  <summary>💡Tips💡</summary>

  - (1st part) Increase waits in the `box1` alias if you don't have enough time to press the keys before hitting the changelevel trigger
  - Make sure you don't accidentally move the box by walking into it before you start the script
  - The first part of the script makes an autosave so you can load back and retry if necessary
  - The second part makes an autosave before the second changelevel
  - It's recommended to spam both scripts
  
</details>

[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/bp_box.sav)




## **D. Power Up**
  
### 11. Changelevel delay scripts

#### 🟡 Power Up A
*Made by [Parklez](https://github.com/parklez)*
- The most widely used one
- Backwards movement
- Does an object boost
```
alias puskip_a "fps_max 100; -jump;-moveright;-moveleft;speak fvox/power_level_is;w 100;speak fvox/beep;w 100;speak fvox/beep;w 100;speak fvox/beep;w 100;speak fvox/beep;w 100;speak fvox/beep;w 100;speak fvox/beep;cl_pitchdown 180;cl_pitchup -179;w 30;cl_pitchup -30;cl_pitchdown 31;w;cl_pitchup 89;cl_pitchdown 89;w 10;+use;w 11;-use;+jump;w;-jump; weapon_tripmine"
```
Example: `bind key puskip_a`\
Usage: Throw a nade under the box at 20 fps to nuke everything, walk into the changelevel trigger holding `s` and activate the script before touching it. Use mouse movement to control the character, pickup tripmines and get stuck into the corner\
[Video link](https://youtu.be/IkZ4wWKrLVg)\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/puskip.sav)


#### 🟢 Power Up B
*Made by [Parklez](https://github.com/parklez)*
- Simplest (and slowest) version
- Facing forward
- No object boost
```
alias puskip_b "fps_max 100; speak fvox/power_level_is;w 100;speak fvox/beep;w 100;speak fvox/beep;w 100;speak fvox/beep;w 100;speak fvox/beep;w 100;speak fvox/beep;w 50; weapon_tripmine"
```
Example: `bind key puskip_b`\
Usage: Throw a nade under the box at 20 fps to nuke everything, walk into the changelevel trigger holding `w` and activate the script before touching it. Use mouse movement to control the character and go to the wall, picking up tripmines on the way\
[Video link](https://youtu.be/B4_AL1Mtu4g)\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/puskip.sav)


#### 🟠 Power Up D
*Made by Wize*
- Facing forward
- With object boost (1400 UPS)
- Makes an autosave when activated
```
alias puskip_d "fps_max 100; save autosave;weapon_shotgun;-jump;-moveright;-moveleft;w 300;+use;w 7;-use;+jump;w;-jump;+attack2;w;-attack2;+duck;w 37;-duck;weapon_tripmine"
```
Example: `bind key puskip_d`\
Usage: Break 2 crates containing tripmines, do an object boost with obbo1600 or obbo2000 script, make sure the box you boost with doesn't get stuck! You want to push it far enough to be able to boost with it again during CLD. Hold `w` and press the script key before touching the changelevel trigger, then use mouse movement to go to the box you left behind and wait until the script ends\
[Video link](https://youtu.be/e4KVJcd7h14)\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/puskip.sav)


#### 🔴 Power Up F
*[Power Up D](#-power-up-d) modified by javac_*
- Fastest version
- Facing forward
- With object boost (1800 UPS)
- Makes an autosave when activated
```
alias puskip_f "fps_max 100; save autosave;weapon_shotgun;-jump;-moveright;-moveleft;w 300;+use;w 7;-use;+jump;w;-jump;+attack2;w;-attack2;+duck;w 37;-duck;weapon_tripmine"
```
Example: `bind key puskip_f`\
Usage: Break 2 crates containing tripmines, do an object boost with obbo1600 or obbo2000 script, make sure the box you boost with doesn't get stuck! You want to push it far enough to be able to boost with it again during CLD. Hold `w` and press the script key before touching the changelevel trigger, then use mouse movement to go to the box you left behind and wait until the script ends\
[Video link](https://youtu.be/5R8_ISE3k3A)\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/puskip.sav)
















## **E. Apprehension**

### 12. Obboducktap script
```
alias app_obbo "+use; w 9; -use; w; +duck; w 8; -duck"
```
Example: `bind key app_obbo`\
Usage: drop down, hold A, press the script key. Don't stay too close to the box\
[Video link](https://youtu.be/Vu7-yZZ5hr8)\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/app_obbo.sav)


### 13. ⬛ Captured scripts
#### 🟡 Captured v1
*Made by [Parklez](https://github.com/parklez)*
<details>
  <summary>📜Click here to view the script📜</summary>
  
```
alias captured ct1
alias ct1 "fps_max 100;w 2205;alias captured ct2"
alias ct2 "w 164;alias captured ct3"
alias ct3 "w 6;+speed;w 21;-right;-speed;alias captured ct4"
alias ct4 "w 11;+jump;+duck;w 21;-forward;alias captured ct5"
alias ct5 "w 15;-moveright;-right;w 50;alias captured ct6"
alias ct6 "w 30;-duck;-jump;-moveleft;-left;w 40;cl_pitchdown 89.999;cl_pitchup -89.999;w;+use;w;-use;w;alias captured ct7"
alias ct7 "w;-forward;w;alias captured ct8"
alias ct8 "w;-forward;w;alias captured ct9"
alias ct9 "w;-forward;w;alias captured ct10"
alias ct10 "w;-forward;w;+use;w;-use;cl_pitchup 89;cl_pitchdown 89; alias captured"

// binds
bind 7 captured
```
</details>

<details>
  <summary>📋Usage📋</summary>

Lower fps to 8 before the changelevel, press the first script key as soon as you see the "loading..." text on the screen, then press the rest of the keys
- **Keypresses**:
```
7
s + 7
rightarrow + 7
w + 7
d + rightarrow + 7
a + leftarrow + 7
w + 7
w + 7
w + 7
w + 7   
```
  
</details>

[Video link](https://youtu.be/5-jEl8-MREc)\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/captured.sav)


#### 🟡 Captured v1.2
[Captured v1](#-captured-v1) 2-key edition
<details>
  <summary>📜Click here to view the script📜</summary>
  
```
alias ct1 "fps_max 100; w 2205; alias ctmove +back; alias ct ct2" // 0
alias ct2 "w 164; -back; alias ctmove +right; alias ct ct3" // 90
alias ct3 "w 6; +speed; w 21; -right; -speed; alias ctmove +forward; alias ct ct4" // 90
alias ct4 "w 11; +jump; +duck; w 21; -forward; alias ctmove +moveright; alias ct ct5" // 90
alias ct5 "alias ctmove +right; alias ct ct6" // 90
alias ct6 "w 15; -moveright; -right; w 50; alias ctmove +moveleft; alias ct ct7" // 90
alias ct7 "alias ctmove +left; alias ct ct8" // 90
alias ct8 "w 30; -duck; -jump; -moveleft; -left; w 40; cl_pitchdown 89.999; cl_pitchup -89.999; w; +use; w; -use; w; alias ctmove +forward; alias ct ct9" // 90
alias ct9 "w; -forward; w; alias ct ct10" // 90
alias ct10 "w; -forward; w; alias ct ct11" // 90
alias ct11 "w; -forward; w; alias ct ct12" // 90
alias ct12 "w; -forward; w; +use; w; -use; cl_pitchup 89; cl_pitchdown 89; alias ctmove; alias ct" // 90
alias ct ct1
alias ctmove


// binds
bind 0 ct
bind 9 ctmove
```
</details>

<details>
  <summary>📋Usage📋</summary>

Lower fps to 8 before the changelevel, press the first script key as soon as you see the "loading..." text on the screen, then press the rest of the keys
- **Keypresses**:
  - `0 90 90 90 90 90 90 90 90 90 90 90` (`0` and then `90` eleven times)
  
</details>

[Video link](https://youtu.be/XqQ8PqylHC0)\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/captured.sav)


#### 🟠 Captured v2
*made by javac_*
- Slightly faster
<details>
  <summary>📜Click here to view the script📜</summary>
  
```
alias capt1 "sensitivity 0; fps_max 40; w 800; alias captmv +right; alias capt capt2" // 0
alias capt2 "w 8; -right; w 8; alias captmv +back; alias capt capt3" // 90
alias capt3 "w 40; -back; w 86; fps_max 100; w 56; alias captmv +forward; alias capt capt4" // 90
alias capt4 "w 11; +jump; +duck; w 3; -forward; w 10; alias captmv +moveright; alias capt capt5" // 90
alias capt5 "alias captmv +right; alias capt capt6" // 90
alias capt6 "w 18; -right; -moveright; w 25; alias captmv +moveleft; alias capt capt7" // 90
alias capt7 "alias captmv +left; alias capt capt8" // 90
alias capt8 "w 15; -moveleft; -left; -jump; w 35; -duck; w 7; +use; w; -use; alias captmv +forward; alias capt capt9" // 90
alias capt9 "w; -forward; w; alias capt capt10" // 90
alias capt10 "w; -forward; w; alias capt capt11" // 90
alias capt11 "w; -forward; w; alias capt capt12" // 90
alias capt12 "alias captmv; w; -forward; +use; w; -use; alias capt; capt_sens" // 90
alias capt capt1
alias captmv


// settings
alias capt_sens "sensitivity 3"

// binds
bind 0 capt
bind 9 captmv
```
</details>

<details>
  <summary>📋Usage📋</summary>

Lower fps to 8 before the changelevel, press the first script key as soon as you see the "loading..." text on the screen, then press the rest of the keys
- **Keypresses**:
  - `0 90 90 90 90 90 90 90 90 90 90 90` (`0` and then `90` eleven times)
- **Additional actions**:
  - change sensitivity in the `capt_sens` alias to your default
  
</details>

[Video link](https://youtu.be/FM-C0JTUf3A)\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/captured.sav)






## **F. Residue Processing**

### 14. 🥩 Meatgrab scripts
#### 🟢 Simple meatgrab
```
alias meatgrab "fps_max 100;+use;w 15;-use"
```
Example: `bind key meatgrab`
<details>
  <summary>📋Usage📋</summary>

  Start holding `d` and press the script key after you pass the right edge of the meat. Ideally you want to get a 14XX UPS boost, but sometimes 1300 or 1500 will work as well. You should also delay the first jumpp in order to maintain speed and avoid fall damage. To keep the optimal speed, start holding jump key after the first drop in the pipe (when your velocity drops down do ~700)
</details>

[Video link](https://youtu.be/sa3lghAIK9E)\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/meatgrab.sav)


#### 🟡 Advanced meatgrab
```
alias meatgrab2 "fps_max 100; +use; w 15; -use; -moveright; w 8; +jump; w 3; -jump; fps_max 20; w 10; fps_max 100"
```
Example: `bind key meatgrab2`\
Usage: same setup as [Simple meatgrab](#-simple-meatgrab), but you can start holding `+jump` key instantly\
[Video link](https://youtu.be/Z9tLJuKtTAY)\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/meatgrab.sav)


#### 🟠 2-key meatgrab v1
*Made by mxpph*
```
alias mg mg1
alias mg1 "fps_max 100;+duck;w 50;alias mg mg2"
alias mg2 "+use;w 18;-use;w 20;fps_max 20;w 4;fps_max 100;-duck;alias mg mg1"
```
Example: `bind key mg`
<details>
  <summary>📋Usage📋</summary>

1. Move meat like for the regular setup, look perpendicularly (yaw ~`180`)
2. Press `key d key` in a quick  succession (`key` is the script key)
3. Hold `+jump` after the script is done  
</details>

[Video link](https://youtu.be/0LMERpfvifc)\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/meatgrab.sav)


#### 🔴 2-key meatgrab v2
Slightly modified [v1](#-2-key-meatgrab-v1). Higher exit speed
```
alias mtg mtg1
alias mtg1 "fps_max 100;+duck;w 50;alias mtg mtg2"
alias mtg2 "+use;w 18;-use;w 60;-duck;alias mtg mtg1"
```
Example: `bind key mtg`\
Usage: same as [v1](#-2-key-meatgrab-v1)\
[Video link](https://youtu.be/wiJWJ3Cdykc)\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/meatgrab.sav)




### 15. 💥 RP clipping scripts
#### 🟢 RP clipping 80 hp ver.
*Made by Tankfird & jorikgrozniy, modified by Kisimov*
- Requirements: 80 hp, 0 armor
```
alias rp_80 "cl_pitchdown 89;cl_pitchup -89;fps_max 20.2;+attack;w;weapon_crowbar;-attack;w 32;-forward; +jump; weapon_handgrenade;w;-jump;+duck;w 20;w 10;fps_max 20;w 10;-duck;fps_max 100;cl_pitchdown 89;cl_pitchup 89"
```
Example: `bind key rp_80`\
Usage: hold `w` and activate the script after you pass the gray pipe on the floor\
[Video link](https://youtu.be/Ho4tTNmveC4)\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/rpclipping.sav)


#### 🟡 RP clipping 75 hp ver.
*Made by javac_, [idea](https://youtu.be/RB6xVRVnwfw) by Tankfird*
- Requirements: 75 hp, 0 armor
```
alias rp_75 "fps_max 19.9; cl_pitchdown 89;cl_pitchup -89; +attack; w 30; +jump; +duck; -forward; w; -jump; w 10; fps_max 6.41; w; fps_max 19.85; w 5; -attack; w 5; cl_pitchdown -89; cl_pitchup 89; w 14; -duck; cl_pitchdown 89; force_centerview; fps_max 100"
```
Example: `bind key rp_75`\
Usage: hold `w` and activate the script after you pass the gray pipe on the floor\
[Video link](https://youtu.be/50h5JHY5WvI)\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/rpclipping.sav)




## **G. Surface Tension**
### 16. CLD scripts

#### 🟢 ST CLD v1
*Made by Wize*
- More consistent version
<details>
  <summary>📜Click here to view the script📜</summary>
  
```
alias st0 "bxt_autojump 1; fps_max 100; alias stmove +forward; w 40; alias stskip st1" // 1
alias st1 "weapon_gauss;+duck;w 146;-duck;-forward;alias stskip st2;alias stmove +moveright" // 2+1
alias st2 "+attack2;w 150;-moveright;+use;w 2;-use;alias stskip st3;alias stmove +forward" // 2+1
alias st3 "w 15;+jump;cl_pitchup 180;cl_pitchdown -180;-attack2;w;cl_pitchup 89;cl_pitchdown 89;force_centerview;-forward;w 60;alias stskip st4;alias stmove +moveright" // 2+1
alias st4 "alias stmove +right; alias stskip st5" // 2+1
alias st5 "alias stmove; w 26;-right;-moveright;w 30;-jump;cl_pitchup -89;cl_pitchdown 89;w 44;cl_pitchup 89;weapon_shotgun;alias stskip" // 2+1

alias stskip st0
alias stmove


// binds
bind 1 stskip
bind 2 stmove
```
</details>
<details>
  <summary>📋Usage📋</summary>

Switch to the gauss, aim at the cliff corner. Try to be as fast as possible to avoid getting damage. Also it's *highly* recommended to have some armor so the helicopter shots don't change player's position much (good for consistency)
- **Keypresses**: `1 21 21 21 21 21` (`1` and then `21` five times)
  
</details>

[Video link](https://youtu.be/Rf5UCa3_MP4)\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/st_cld.sav)


#### 🟡 ST CLD v2
*Made by javac_*
- Faster version
- Lower chance of taking damage
<details>
  <summary>📜Click here to view the script📜</summary>
  
```
alias tau "cl_pitchup 180;cl_pitchdown -180;-attack2;w;cl_pitchup 89;cl_pitchdown 89;force_centerview"
alias sst1 "bxt_autojump 1; fps_max 100; weapon_gauss; sstdelay; +attack2; alias sstmove +forward; alias sst sst2" // 2
alias sst2 "w 20; alias sstmove +moveleft; alias sst sst3" // 1+2
alias sst3 "w 90; -moveleft; w 10; -forward; alias sst sst4" //  1+2
alias sst4 "alias sstmove +left; alias sst sst5" // 1+2
alias sst5 "w 10; +jump; w 28; -left; -moveleft; w 15; tau; w 10; +attack2; w 40; alias sstmove +moveright; alias sst sst6" // 1+2
alias sst6 "alias sstmove +right; alias sst sst7" // 1+2
alias sst7 "alias sstmove; w 30; -moveright; -right; tau; w 25; -jump; cl_pitchdown 89; cl_pitchup -89; w 22; weapon_shotgun; cl_pitchup 89; alias sst" // 1+2

alias sst sst1
alias sstmove


// settings
alias sstdelay "w 100"

// binds
bind 2 sst
bind 1 sstmove
```
</details>
<details>
  <summary>📋Usage📋</summary>

Switch to the gauss, hold crouch, go into the corner, uncrouch, aim at the edge of the cliff (not really precise). Try to be as fast as possible to avoid getting damage. Also it's *highly* recommended to have some armor so the helicopter shots don't change player's position much (good for consistency)
- **Keypresses**: `2 12 12 12 12 12 12` (`2` and then `12` six times)
- **Additional actions**: increase delay in the `sstdelay` alias if you don't have enough time to press the script keys
  
</details>

[Video link](https://youtu.be/86eRINHTYZg)\
[Practice save](https://github.com/yavats/hl1-scripts/raw/refs/heads/main/Practice%20saves/st_cld.sav)




### 20. HL21 P2P Scripts

<details>
  <summary>📜Click Here To View Scripts📜</summary>

#### 🟢 Jorik's P2P Script
- ❗You must edit ptpsens value to your normally used sensitivity value❗
- ❗If you are too slow at pressing keys, increase ptpdelay value❗
- ❗If you want to change keybinds, pay attention to the order❗
```
alias ptpscript ptp0
alias ptpmove1 +moveleft
alias ptpmove2 +forward
alias ptptau "cl_pitchup 180;cl_pitchdown -180;-attack2;wait;cl_pitchup 89;cl_pitchdown 89;force_centerview"
alias ptpre "-forward;-moveleft;-moveright;-duck;-jump;-right;-left;-attack2;ptpsens;alias ptpscript ptp0;alias ptpmove2 +forward;alias ptpmove1 +moveleft" // use if you failed keys order
alias ptpsens "sensitivity 0.6" // change it (sensitivity after script done)
alias ptpdelay "w 200" // change it (start delay, increase it if you dont have time to press keys, every w 100 = 1 sec)

alias ptp0 "sensitivity 0;ptpdelay;alias ptpscript ptp1"
alias ptp1 "+attack2;w 52;-forward;-moveleft;+jump;alias ptpscript ptp2;alias ptpmove2 +moveright"
alias ptp2 "+duck;w 70;-moveright;alias ptpscript ptp3;alias ptpmove2 +moveleft"
alias ptp3 "-jump;w 20;-moveleft;-duck;alias ptpscript ptp4;alias ptpmove2 +right"
alias ptp4 "w 38;-right;w 10;alias ptpscript ptp5;alias ptpmove2 +moveleft"
alias ptp5 "w 18;-moveleft;w 10;force_centerview;alias ptpscript ptp6;alias ptpmove2 +forward"
alias ptp6 "w 16;ptptau;w;-forward;alias ptpscript ptp7;alias ptpmove2 +moveright"
alias ptp7 "w 10;+attack2;w 70;alias ptpscript ptp8;alias ptpmove2 +right"
alias ptp8 "w 6;-right;-moveright;alias ptpscript ptp9;alias ptpmove2 +back"
alias ptp9 "w 2;-back;+jump;w 70;alias ptpscript ptp10;alias ptpmove2 +left"
alias ptp10 "w 5;-left;-moveleft;-jump;ptptau;w;save autosave;w 71;alias ptpscript ptp11;alias ptpmove2 +right;alias ptpmove1 +moveright"
alias ptp11 "w 4;-right;w 2;-moveright;+duck;w 10;fps_max 20;+use;w 4;-duck;fps_max 100;w 15;-use;ptpsens;alias ptpscript ptp0;alias ptpmove2 +forward;alias ptpmove1 +moveleft"

bind k ptpscript
bind j ptpmove2
bind h ptpmove1


```
  </details>
  
<details>
  <summary>📋Usage📋</summary>
  
- Start manually charge gauss when you entered map
- Go to the corner i showed in the video
- Aim at the corner i showed in the video (yaw is ~268.70 - ~268.90 , pitch almost doesnt matter but its around 6.0)
- Press keys in order after you aimed (and release +attack2 key after you pressed first script key):
  -  k
  - h j k
  - j k (8x)
  - h j k (2x)
  
 </details>

 <details>
  <summary>📼Video Guide📼</summary>
  
  https://github.com/user-attachments/assets/ffbffe26-d0c3-4f61-983f-51a2d8b2e2bd
  
  </details>

 #### 🟡 Javac's Hole In One P2P Script

  
 </details>

 ### 21. Slowgauss After Ihd Door
 ❗For slowgauss to work you need either 1 or 2 ammo left on your gauss❗
 ❗Recommended to have 2 ammo if possible, then you will have 1 more ammo left for another slow gauss to break the cage later❗
 
 ```
alias tausloo "cl_pitchup 180;cl_pitchdown -180;-attack;w50;cl_pitchup 89.999;cl_pitchdown 89.999;force_centerview"
```
Example: `bind key tausloo`

<details>
  <summary>📼Video Guide📼</summary>
  
https://github.com/user-attachments/assets/7a8a3b3c-8ccb-4cb5-8b81-b74e16819707

  </details>

### 22. Nadeboost For New ST Route
```
alias boostx "+duck;w19;cl_pitchup -96;cl_pitchdown -180;wait;+attack2;wait;-attack2;w2;-duck;cl_pitchup 89.999;cl_pitchdown 89.999;force_centerview"
```
Example: `bind key boostx`

<details>
  <summary>📼Video Guide📼</summary>
  
https://github.com/user-attachments/assets/954369ee-eb51-4a2e-82ff-80e47a811c3c

  </details>

## **L. Forget About Freeman**

### 23. Chairboost Script
- ❗The "usekey" in here must be your standard +use key❗
  ```
  alias fafobbo "obbo1300; wait; bind e +use"
  ```
Example: `bind key "bind usekey fafobbo; say fafobbo"`

### 24. CLD Scripts

<details>
  <summary>📜Click Here To View Scripts📜</summary>

#### 🟢 Smg CLD
```
alias "faf_e" "fps_max 100; save autosave; weapon_crowbar; -moveleft; +attack;w 350;-attack;force_centerview;weapon_9mmAR;cl_pitchdown 180;cl_pitchup -179;w 40;cl_pitchup 89;cl_pitchdown 89;w 30;+jump;+duck;w;cl_pitchdown 136;cl_pitchup -135;-forward;+attack2;w 30;-attack2;cl_pitchup 89;cl_pitchdown 89;force_centerview;-jump;-duck;w 10;+duck;w 16;-duck; weapon_hornetgun"
```
Example: `bind key faf_e`

<details>
  <summary>📼Video Guide📼</summary>

https://github.com/user-attachments/assets/e3635e60-279f-4404-9e5e-f20b57c2512a

  </details>

#### 🟡 Smg CLD with fast ladder climb


#### 🟠 Grenade CLD
```
alias faf "save quick;speak fvox/power_level_is.beep._comma.beep._comma.beep._comma.beep;-moveright;-moveleft;-duck;weapon_crowbar;+attack;w 500;weapon_handgrenade;w 40;cl_pitchdown 180;cl_pitchup -179;w 40;cl_pitchup 89.999;cl_pitchdown 89.999;cl_pitchup -40;cl_pitchdown 40.001;w 30;-attack;w 4;+jump;+duck;wait;-jump;-duck;cl_pitchup 89;cl_pitchdown 89;w 61"
```
Example: `bind key faf`

<details>
  <summary>📼Video Guide📼</summary>
  
 [link](https://www.youtube.com/watch?v=E4h4jmzd-gI)\

 </details>

#### 🔴 Grenade CLD + Smg nade to scare vortigaunts
```
alias faf "w 400;smg;w 1;weapon_handgrenade;w 10;+attack;w 50;cl_pitchdown 180;cl_pitchup -179;w 40;cl_pitchup 89.999;cl_pitchdown 89.999;cl_pitchup -40;cl_pitchdown 40.001;w 30;-attack;w 4;+jump;+duck;w 1;-jump;-duck;cl_pitchup 89.999;cl_pitchdown 90;w 61"
alias smg "cl_pitchdown 180;cl_pitchup -179;w 1;+attack2;w 1;cl_pitchup 89;cl_pitchdown 89;-attack2"
```
📋Usage📋: `same as grenade cld but cook the grenade and switch to the SMG before activating.`
Example: `bind key faf`

</details>

## **M. Lambda Core**

### 25. Watergauss Clip Script
- ❗If you don't have enough time to get into the corner, increase alias "dst" value❗
```
alias _taubow
alias _taubofuncw "cl_pitchup 180;cl_pitchdown -180;-attack;wait;cl_pitchup -12;cl_pitchdown 12;wait;cl_pitchup 89.999;cl_pitchdown 89.999"
alias +tauw "+attack; alias _taubow _taubofuncw"
alias -tauw "_taubow; alias _taubow"

alias fps_20 "fps_max 20"
alias fps_100 "fps_max 100"
alias +wc "+duck;w;-duck;w5;+duck;w30;-duck;w60;gwc;w10;wwc"
alias -wc "-tauw;-attack2;"
alias wwc "fps_20;dst;-forward;-moveright;-wc;w;fps_100;weapon_handgrenade"
alias gwc "w5;-attack2;+tauw;w;"
alias dst "w8" (WAITING VALUE FOR SHOOTING. INCREASE IT IF YOU DONT HAVE ENOUGH TIME)
```

<details>
  <summary>📼Video Guide📼</summary>
  
https://github.com/user-attachments/assets/bce50158-6c12-410f-a647-aedc00a3a27b

  </details>
  
Example: `bind key "+wc"`

### 26. Smg Boost Scripts



## **N. Xen**

### 27. Jumpbugs

#### 🟢 Viewsnap + Fps switch
- ❗Change xenv_sens value to your normal sensitivity value before use❗
```
bind f1 xenv // script bind
bind o +bxt_tas_jumpbug // jumpbug bind

alias xenv_sens "sensitivity 2.37" // your default sens

alias xenv xenv1
alias xenv1 "+attack2; w 10; weapon_gauss; +attack2; +duck; bxt_autopause 1; fps_max 97; cl_pitchup -35.83; cl_pitchdown 35.83; m_pitch 0; sensitivity 1819.54545; say xen_strat; xenv_reset; alias xenv xenv2"
alias xenv2 "sensitivity 0; unpause; +attack2; w 10; -attack2; fps_max 97; w 40; w 10; -duck; bxt_autopause 0; xenv_sens; cl_pitchup 89; cl_pitchdown 89; m_pitch 0.022; fps_max 33.33333; alias xenv xenv1"
```
<details>
  <summary>📋Usage📋</summary>
  
- Go through portal and immediately start charging
- Meanwhile charging press the script bind (❗you can release attack2 after pressing keybind script will charge itself!❗)
- After changelevel, game will be autopaused, set viewangle, unpause the game, and hold your jumpbug bind to hit the jumpbug
  
  </details>

<details>
  <summary>📼Video Guide📼</summary>

https://github.com/user-attachments/assets/1df2eb19-dc8d-4264-9340-5d9c057f2a1d

  </details>

#### 🟡 Viewsnap (Fully automatic) [❗NOT RECOMMENDED, VERY INCONSISTENT❗]
```
bind f1 xenv

alias xenv_sens "sensitivity 2.37"
alias xenv_binds_set "bind 2 xenv_dolb; bind 3 xenv_mv1; bind 4 xenv_mv2"
alias xenv_binds_def "bind 2 slot2; bind 3 weapon_9mmAR; bind 4 weapon_shotgun"

alias xenv_reset "alias xenv_dolb xenv_dolb1; alias xenv_mv1 +moveright; alias xenv_mv2 +left"
alias xenv "+duck; bxt_autopause 1; fps_max 97; cl_pitchup -35.83; cl_pitchdown 35.83; m_pitch 0; sensitivity 1819.54545; say xen_strat; xenv_reset; xenv_binds_set"

alias xenv_dolb1 "sensitivity 0; unpause; +attack2; w 10; -attack2; fps_max 97; r_norefresh 1; w 40; +attack2; w 10; alias xenv_dolb xenv_dolb2"
alias xenv_dolb2 "w 14; -duck; w 58; -moveright; w 4; -attack2; w 85; -left; w 63; alias xenv_mv1 +moveleft; alias xenv_dolb xenv_dolb3"
alias xenv_dolb3 "w 13; -left; -moveleft; +bxt_tas_jumpbug; bxt_autopause 0; w 30; -bxt_tas_jumpbug; r_norefresh 0; xenv_sens; cl_pitchup 89; cl_pitchdown 89; m_pitch 0.022; fps_max 100; weapon_shotgun; alias xenv_mv1; alias xenv_mv2; xenv_binds_def"
```
<details>
  <summary>📋Usage📋</summary>
  
- First change the sensitivity in xenv_sens
- And change xenv_binds_set (the script keys) and xenv_binds_def (your normal weapon binds)
- Press xenv key before the changelevel after entering the portal. DON'T HOLD +DUCK, IT'LL BREAK THE SCRIPT!
- Set viewangle
- Press in order (for keys 1=xen_dolb 2=xenv_mv1 3=xenv_mv2):
  - 123 (2x)
  - 1
  
  </details>

  <details>
  <summary>📼Video Guide📼</summary>

https://github.com/user-attachments/assets/1356e7f6-a6c1-4852-875f-641789c8ff70

  </details>
  










  





 

 






















