# Module-CrestronVideoWallRouter_4x2
This module is designed to route and set the Video Wall Scaler Modes for compatable DM devices.

This module DOES NOT route a video source to the full 4x2. It will only route in 2x2 quadrants.

The outputs of your video wall needs to be as depicted:

      +---------------+
      ¦ 1 ¦ 3 ¦ 5 ¦ 7 ¦
      -----------------
      ¦ 2 ¦ 4 ¦ 6 ¦ 8 ¦
      +---------------+

When you set a Video Wall Mode, the routes are saved in a structure. When changing Video Wall Modes, these routes will be recalled if the mode has been used before. This is to prevent routing artifacts from occuring.


For example:

default Mode 0:<br>
user routes input 2 to A<br>
user routes input 3 to B<br>
<br>
user sets Mode 1<br>
user routes input 4 to 1<br>
user routes input 5 to 2<br>
user routes input 6 to 3<br>
user routes input 7 to 4<br>
user routes input 8 to B<br>
<br>
user sets Mode 0<br>
Module will route input 2 to A<br>
Module will route input 3 to B<br>
<br>
user sets Mode 1<br>
Module will route input 4 to 1<br>
Module will route input 5 to 2<br>
Module will route input 6 to 3<br>
Module will route input 7 to 4<br>
Module will route input 8 to B<br>

"MODE" Valid Ranges:<br>

MODE = 0

      +-------+-------+
      ¦       ¦       ¦
      ¦  A(1) ¦  B(5) ¦
      ¦       ¦       ¦
      +-------+-------+
<br>
MODE = 1
      
      +---------------+
      ¦ 1 ¦ 3 ¦       ¦
      ¦---+---+  (5)  ¦
      ¦ 2 ¦ 4 ¦       ¦
      +---------------+

MODE = 2

      +---------------+
      ¦ 1 ¦       ¦ 7 ¦
      ¦---+  (3)  +---¦
      ¦ 2 ¦       ¦ 8 ¦
      +---------------+

MODE = 3

      +---------------+
      ¦       ¦ 5 ¦ 7 ¦
      ¦  (1)  +---+---¦
      ¦       ¦ 6 ¦ 8 ¦
      +---------------+

MODE = 4

      +---------------+
      ¦ 1 ¦ 3 ¦ 5 ¦ 7 ¦
      ¦---+---+---+---¦
      ¦ 2 ¦ 4 ¦ 6 ¦ 8 ¦
      +---------------+

Scaler Modes Analog Values:<br>
X1-Y1 = 2211d<br>
X1-Y2 = 2212d<br>
X2-Y1 = 2221d<br>
X2-Y2 = 2222d<br>

The following analog inputs are valid when routing sources to outputs:<br>

Mode 0:<br>
Source_01_val# = DEST_X1-Y1_Source_val#<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;DEST-Y2_Source_val#<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;DEST_X2-Y1_Source_val#<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;DEST_X2-Y2_Source_val#<br>
Source_05_val# = DEST_X3-Y1_Source_val#<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;DEST_X3-Y2_Source_val#<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;DEST_X4-Y1_Source_val#<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;DEST_X4-Y2_Source_val#<br>

Mode 1:<br>
Source_01_val# = DEST_X1-Y1_Source_val#<br>
Source_02_val# = DEST_X1-Y2_Source_val#<br>
Source_03_val# = DEST_X2-Y1_Source_val#<br>
Source_04_val# = DEST_X2-Y2_Source_val#<br>
Source_05_val# = DEST_X3-Y1_Source_val#<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;DEST_X3-Y2_Source_val#<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;DEST_X4-Y1_Source_val#<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;DEST_X4-Y2_Source_val#<br>

Mode 2:<br>
Source_01_val# = DEST_X1-Y1_Source_val#<br>
Source_02_val# = DEST_X1-Y2_Source_val#<br>
Source_03_val# = DEST_X2-Y1_Source_val#<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;DEST_X2-Y2_Source_val#<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;DEST_X3-Y1_Source_val#<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;DEST_X3-Y2_Source_val#<br>
Source_07_val# = DEST_X4-Y1_Source_val#<br>
Source_08_val# = DEST_X4-Y2_Source_val#<br>

Mode 3:<br>
Source_01_val# = DEST_X1-Y1_Source_val#<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;DEST_X1-Y2_Source_val#<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;DEST_X2-Y1_Source_val#<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;DEST_X2-Y2_Source_val#<br>
Source_05_val# = DEST_X3-Y1_Source_val#<br>
Source_06_val# = DEST_X3-Y2_Source_val#<br>
Source_07_val# = DEST_X4-Y1_Source_val#<br>
Source_08_val# = DEST_X4-Y2_Source_val#<br>

Mode 4:<br>
Source_01_val# = DEST_X1-Y1_Source_val#<br>
Source_02_val# = DEST_X1-Y2_Source_val#<br>
Source_03_val# = DEST_X2-Y1_Source_val#<br>
Source_04_val# = DEST_X2-Y2_Source_val#<br>
Source_05_val# = DEST_X3-Y1_Source_val#<br>
Source_06_val# = DEST_X3-Y2_Source_val#<br>
Source_07_val# = DEST_X4-Y1_Source_val#<br>
Source_08_val# = DEST_X4-Y2_Source_val#<br>

