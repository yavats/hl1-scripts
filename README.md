# hl1-scripts
* [Basic Scripts](##Basic-Scripts)


## **Basic Scripts**

### 1. Usespam Script

```
alias +usespam "alias _zspecial @use;@use1"
alias -usespam "alias _zspecial;-use"
alias @use1 "+use;alias @use @use2;bxt_append _zspecial"
alias @use2 "w;alias @use @use3;bxt_append _zspecial"
alias @use3 "-use;alias @use @use4;bxt_append _zspecial"
alias @use4 "w;alias @use @use1;bxt_append _zspecial"
```
Example: `bind e +usespam`

### 2. Duckspam Script
```
alias ds1 "+duck; alias ds ds2; bxt_append ds"
alias ds2 "wait; alias ds ds3; bxt_append ds"
alias ds3 "-duck; alias ds ds4; bxt_append ds"
alias ds4 "wait; alias ds ds1; bxt_append ds"
alias +ds "ds1"
alias -ds "alias ds; -duck"
```
Example `bind t +ds`

### 3. Fps Hold Script/ 4 Fps Script
> If you want other value, just change the first fps value (20 fps on here) and change the name of the alias 
```
alias fps_20 "fps_max 20"
alias fps_default "fps_max 100"

alias +fps_20_hold "fps_20; alias -fps_20_hold fps_20_reset"
alias fps_20_reset "fps_default; alias -fps_20_hold"
```
Example: `bind e +fps_20_hold`
> 4 Fps Script
```
alias 4fpsbind "fps_max 4; wait; fps_max 100"
```
Example: `bind e 4fpsbind`
### 4. Tau Gauss Script (180° Gauss Boosting)
```
alias _taubo
alias _taubofunc "cl_pitchup 180;cl_pitchdown -180;-attack2;wait;cl_pitchup -12;cl_pitchdown 12;wait;cl_pitchup 89;cl_pitchdown 89"
alias +tau "+attack2; alias _taubo _taubofunc"
alias -tau "_taubo; alias _taubo"
```
Example: `bind mouse2 +tau`

### 5. Object Boost Scripts
<details>
  <summary>Click Here To View Scripts</summary>
  
> 2000 Speed Object Boost
```
alias obbo2000 "+use;w 11;-use;+jump;w;-jump"
```
Example: `bind e obbo200`

> 1500 Speed Object Boost
```
alias obbo1500 "+use;w 10;-use;+jump;w;-jump"
```
Example: `bind e obbo1500`

> 1300 Speed Object Boost
```
alias obbo1300 "+use;w 9;-use;+jump;w;-jump"
```
Example: `bind e obbo1300`

> 1000 Speed Object Boost
```
alias obbo1000 "+use;w 8;-use;+jump;w;-jump"
```
Example: `bind e obbo1000`

> 800 Speed Object Boost
```
alias obbo800 "+use;w 7;-use;+jump;w;-jump"
```
Example: `bind e obbo800`

> 600 Speed Object Boost
```
alias obbo600 "+use;w 6;-use;+jump;w;-jump"
```
Example: `bind e obbo600`

> 500 Speed Object Boost
```
alias obbo500 "+use;w 5;-use;+jump;w;-jump"
```
Example: `bind e obbo500`
</details>



### 6. Wait Table (BunnyModXT has its own wait table built on it, but some old scripts uses this wait table so you might need them. Just put this at the very bottom of your config.)
<details>
  <summary>Click Here To View Script</summary>
  
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
