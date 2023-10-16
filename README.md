# Module-CrestronVideoWallRouter_4x2
This module is designed to route and set
the Video Wall Scaler Modes for compatable
DM devices.

IF "[DEBUG]" is anebled, see Text Console
for debug trace statements.

This module DOES NOT route a video source
to the full 4x2. It will only route in
2x2 quadrants.

The outputs of your video wall needs to be
as depicted:
+---------------+
¦ 1 ¦ 3 ¦ 5 ¦ 7 ¦
¦---+---+---+---¦
¦ 2 ¦ 4 ¦ 6 ¦ 8 ¦
+---------------+

When you set a Video Wall Mode, the
routes are saved in a structure. When
changing Video Wall Modes, these routes
will be recalled if the mode has been used
before. This is to prevent routing
artifacts from occuring. 

For example:
default Mode 0:
user routes input 2 to A
user routes input 3 to B

user sets Mode 1
user routes input 4 to 1
user routes input 5 to 2
user routes input 6 to 3
user routes input 7 to 4
user routes input 8 to B

user sets Mode 0
Module will route input 2 to A
Module will route input 3 to B

user sets Mode 1
Module will route input 4 to 1
Module will route input 5 to 2
Module will route input 6 to 3
Module will route input 7 to 4
Module will route input 8 to B

"MODE" Valid Ranges:
MODE = 0
   +-------+-------+
   ¦       ¦       ¦
   ¦  A(1) ¦  B(5) ¦
   ¦       ¦       ¦
   +-------+-------+

MODE = 1
   +---------------+
   ¦ 1 ¦ 3 ¦       ¦
   ¦---+---+  B(5) ¦
   ¦ 2 ¦ 4 ¦       ¦
   +---------------+

MODE = 2
   +---------------+
   ¦ 1 ¦       ¦ 7 ¦
   ¦---+  A(3) +---¦
   ¦ 2 ¦       ¦ 8 ¦
   +---------------+

MODE = 3
   +---------------+
   ¦       ¦ 5 ¦ 7 ¦
   ¦  A(1) +---+---¦
   ¦       ¦ 6 ¦ 8 ¦
   +---------------+

MODE = 4
   +---------------+
   ¦ 1 ¦ 3 ¦ 5 ¦ 7 ¦
   ¦---+---+---+---¦
   ¦ 2 ¦ 4 ¦ 6 ¦ 8 ¦
   +---------------+

Scaler Modes Analog Values:
X1-Y1 = 2211d
X1-Y2 = 2212d
X2-Y1 = 2221d
X2-Y2 = 2222d

The following analog inputs are valid
when routing sources to outputs:

Mode 0:
Source_01_val# = DEST_X1-Y1_Source_val#
                 DEST_X1-Y2_Source_val#
                 DEST_X2-Y1_Source_val#
                 DEST_X2-Y2_Source_val#
Source_05_val# = DEST_X3-Y1_Source_val#
                 DEST_X3-Y2_Source_val#
                 DEST_X4-Y1_Source_val#
                 DEST_X4-Y2_Source_val#

Mode 1:
Source_01_val# = DEST_X1-Y1_Source_val#
Source_02_val# = DEST_X1-Y2_Source_val#
Source_03_val# = DEST_X2-Y1_Source_val#
Source_04_val# = DEST_X2-Y2_Source_val#
Source_05_val# = DEST_X3-Y1_Source_val#
                 DEST_X3-Y2_Source_val#
                 DEST_X4-Y1_Source_val#
                 DEST_X4-Y2_Source_val#

Mode 2:
Source_01_val# = DEST_X1-Y1_Source_val#
Source_02_val# = DEST_X1-Y2_Source_val#
Source_03_val# = DEST_X2-Y1_Source_val#
                 DEST_X2-Y2_Source_val#
                 DEST_X3-Y1_Source_val#
                 DEST_X3-Y2_Source_val#
Source_07_val# = DEST_X4-Y1_Source_val#
Source_08_val# = DEST_X4-Y2_Source_val#

Mode 3:
Source_01_val# = DEST_X1-Y1_Source_val#
                 DEST_X1-Y2_Source_val#
                 DEST_X2-Y1_Source_val#
                 DEST_X2-Y2_Source_val#
Source_05_val# = DEST_X3-Y1_Source_val#
Source_06_val# = DEST_X3-Y2_Source_val#
Source_07_val# = DEST_X4-Y1_Source_val#
Source_08_val# = DEST_X4-Y2_Source_val#

Mode 4:
Source_01_val# = DEST_X1-Y1_Source_val#
Source_02_val# = DEST_X1-Y2_Source_val#
Source_03_val# = DEST_X2-Y1_Source_val#
Source_04_val# = DEST_X2-Y2_Source_val#
Source_05_val# = DEST_X3-Y1_Source_val#
Source_06_val# = DEST_X3-Y2_Source_val#
Source_07_val# = DEST_X4-Y1_Source_val#
Source_08_val# = DEST_X4-Y2_Source_val#

