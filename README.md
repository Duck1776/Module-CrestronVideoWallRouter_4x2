[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/Y8Y7PSI74)
# __Video Wall Router 4x2__ 
___

      __         __         __         __         __         __
    <(o )___   <(o )___   <(o )___   <(o )___   <(o )___   <(o )___     GOD BLESS AMERICA
     ( ._> /    ( ._> /    ( ._> /    ( ._> /    ( ._> /    ( ._> /     JULY 4TH, 1776
      `---'      `---'      `---'      `---'      `---'      `---' 
## What does this module do?                                   
This module is designed to route and set the Video Wall Scaler Modes for compatible DM devices. The layout of the video wall is 4 wide by 2 tall, and using (X,Y) coordinates, X1-Y1 would be the top left, and X2-Y2 would be the bottom right. I only account for a 16:9 aspect ratio, so when a set of displays are set to a single display, it will be 2x2. See __[MODES](#modes)__ for layout examples.

To be clear, this module __DOES NOT__ route a video source to the full 4x2. It will only route in 2x2 quadrants.

The outputs of your video wall needs to be as depicted:

![Alt text](image.png)

When you set a Video Wall Mode, the routes are saved in a structure. When changing Video Wall Modes, these routes will be recalled if the mode has been used before. This is to prevent routing artifacts from occurring.


For example:

1. default Mode __0__:
* user routes input __2__ to __A__
* user routes input __3__ to __B__

2. user sets Mode __1__:
* user routes input __4__ to __1__
* user routes input __5__ to __2__
* user routes input __6__ to __3__
* user routes input __7__ to __4__
* user routes input __8__ to __B__

3. user sets Mode __0__:
* Module will route input __2__ to __A__
* Module will route input __3__ to __B__

4. user sets Mode __1__:
* Module will route input __4__ to __1__
* Module will route input __5__ to __2__
* Module will route input __6__ to __3__
* Module will route input __7__ to __4__
* Module will route input __8__ to __B__

## MODES
"MODE" Valid Ranges:<br>

MODE:<br>
0<br>
![Alt text](image-5.png)

1<br> 
![Alt text](image-6.png)

2<br>
![Alt text](image-7.png)

3<br>
![Alt text](image-8.png)

4<br>
![Alt text](image-9.png)



Scaler Modes Analog Values:
* X1-Y1 = 2211d
* X1-Y2 = 2212d
* X2-Y1 = 2221d
* X2-Y2 = 2222d

<br>

The following analog inputs are valid when routing sources to outputs:<br>
> Reference
>* CHANGE TO "Source_##_val#"
>   * EFFECTS "DEST_X#-Y#_Source_val#"

<br>

__Mode 0:__
* Source_01_val#
  * DEST_X1-Y1_Source_val#<br>
  * DEST-X1-Y2_Source_val#<br>
  * DEST_X2-Y1_Source_val#<br>
  * DEST_X2-Y2_Source_val#<br>
* Source_05_val# = DEST_X3-Y1_Source_val#<br>
  * DEST_X3-Y2_Source_val#<br>
  * DEST_X4-Y1_Source_val#<br>
  * DEST_X4-Y2_Source_val#<br>

__Mode 1:__
* Source_01_val#
  * DEST_X1-Y1_Source_val#
* Source_02_val#
  * DEST_X1-Y2_Source_val#
* Source_03_val#
  * DEST_X2-Y1_Source_val#
* Source_04_val#
  * DEST_X2-Y2_Source_val#
* Source_05_val#
  * DEST_X3-Y1_Source_val#
  * DEST_X3-Y2_Source_val#
  * DEST_X4-Y1_Source_val#
  * DEST_X4-Y2_Source_val#

__Mode 2:__
* Source_01_val#
  * DEST_X1-Y1_Source_val#
* Source_02_val#
  * DEST_X1-Y2_Source_val#
* Source_03_val#
  * DEST_X2-Y1_Source_val#
  * DEST_X2-Y2_Source_val#
  * DEST_X3-Y1_Source_val#
  * DEST_X3-Y2_Source_val#
* Source_07_val#
  * DEST_X4-Y1_Source_val#
* Source_08_val#
  * DEST_X4-Y2_Source_val#

__Mode 3:__
* Source_01_val#
  * DEST_X1-Y1_Source_val#
  * DEST_X1-Y2_Source_val#
  * DEST_X2-Y1_Source_val#
  * DEST_X2-Y2_Source_val#
* Source_05_val#
  * DEST_X3-Y1_Source_val#
* Source_06_val#
  * DEST_X3-Y2_Source_val#
* Source_07_val#
  * DEST_X4-Y1_Source_val#
* Source_08_val#
  * DEST_X4-Y2_Source_val#

__Mode 4:__
* Source_01_val#
  * DEST_X1-Y1_Source_val#
* Source_02_val#
  * DEST_X1-Y2_Source_val#
* Source_03_val#
  * DEST_X2-Y1_Source_val#
* Source_04_val#
  * DEST_X2-Y2_Source_val#
* Source_05_val#
  * DEST_X3-Y1_Source_val#
* Source_06_val#
  * DEST_X3-Y2_Source_val#
* Source_07_val#
  * DEST_X4-Y1_Source_val#
* Source_08_val#
  * DEST_X4-Y2_Source_val#

---

[![Duck1776 GitHub stats](https://GitHub-readme-stats.vercel.app/api?username=Duck1776)](https://GitHub.com/anuraghazra/GitHub-readme-stats) 

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/Y8Y7PSI74)