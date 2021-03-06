**PyDiceroll Tutorial**
=======================

.. figure:: dice_tut.png

Rolling the Dice
----------------

Once ``PyDiceroll.py`` is installed and your code is able to import the module, its ``roll()`` function can be
used right away. This function returns an integer, by the way. So it can be used as any other integer would
be used. But first, we must give this function a value to work from.

.. function:: roll(dice)

   | *dice* = a string of three ordered concatenated values:
   |
   | *number_of_dice* + *dice_type* + *dice_roll_modifier*
   |
   | As examples:
   | *dice* = '2' + 'D10' + '-2'
   | *dice* = str(3) + 'D6' + '+2'
   | *dice* = 'FLUX'
   |
   | *dice_roll_modifier* must include a '+' or '-' with its value.
   |
   | Note that both *number_of_dice* and *dice_roll_modifier* are optional, and may not even be
   | used by some *dice_type* rolls.

Those of you that have used dice rolling programs before will notice that something is different. And that is,
``roll()`` uses a string for its input:

>>> die1 = roll('1D6')
>>> die2 = roll('1d6')
>>> dice = '3D4+1'
>>> print(die1, die2+4, roll(dice))
3, 6, 9

The return values from ``roll()`` are always integer.

Notice that the inputted string values can be upper or lower case.

The dice types to roll are:

   **D2, D3, D4, D5, D6, D8, D09, D10, D12, D20, D30, D99, D100, D44, D66, D88,
   DD, BOON, BANE, FLUX, GOODFLUX, BADFLUX, ADVANTAGE, DISADVANTAGE**, and **4dF**.

**D09** rolls will generate a range of **0 - 9**.

**D99** rolls will generate a range of **0 - 99**.

**D2** rolls will generate a range of **0 - 1**.

The **4dF** roll type is for FATE mechanics. A range of **-4 to 4** is generated.

Traveller5 uses **1D** thru **10D** rolls, depending on the difficulty of a task. DMs are supported.

**ADVANTAGE** and **DISADVANTAGE** are dice rolls for the d20 system.


.. note::

   You may recognize some of these dice types from various tabletop role-playing games. Not all dice types are covered by **PyDiceroll**. However, more are planned for in future releases.

**PyDiceroll** uses a simple standard when it comes to rolling various dice types.

Some examples are:

.. literalinclude:: databox1.dat

**PyDiceroll** can be used directly at a CMD prompt using:

The long form:

.. literalinclude:: databox2.dat

Or the short form:

.. literalinclude:: databox3.dat

.. note::

    Typing ``PyDiceroll.py -h`` will provide some help.

A **TEST** roll that calculates percentages for 2D6 can be issued:

>>> roll('test')
      6x6 Roll Chart Test
     1    2    3    4    5    6
1  262  296  250  292  292  241
2  270  315  299  236  279  261
3  295  274  288  274  291  295
4  273  284  279  276  249  273
5  293  280  291  276  280  283
6  270  276  282  272  273  280
            6x6 Roll Chart Percentage
        1       2       3       4       5       6
1   2.62%   5.66%   8.60%  11.38%  13.93%  16.23%
2   5.66%   8.60%  11.38%  13.93%  16.23%  13.95%
3   8.60%  11.38%  13.93%  16.23%  13.95%  11.02%
4  11.38%  13.93%  16.23%  13.95%  11.02%   8.25%
5  13.93%  16.23%  13.95%  11.02%   8.25%   5.56%
6  16.23%  13.95%  11.02%   8.25%   5.56%   2.80%

The roll will return a list of percentages for 2-12 rolled.
