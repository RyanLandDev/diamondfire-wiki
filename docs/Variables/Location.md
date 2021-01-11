# Location

Location variables are variables that record the location of something.

You can acquire the location item (a paper) in the [Values](Other/Code_Related/Values.md) menu (right-click the iron ingot).

Right-click while holding the paper to save the location of your current player to the location paper. Left-click a block while holding the paper to save the location of the block to the location paper. Shift + right-click to get various locations of things such as the projectile, victim, or selection of the event. Shift + left-click to teleport to the location saved on the location paper.

There is also a `/loc` command that allows you to edit and change various aspects of the location paper.

Command | Description
--- | ---
/loc get [amount] | Gives you a certain amount of location items with the location set to the current player's location.
/loc align | Floors the currently held location item's axes.
/loc center | Centers the currently held location item's axes.
/loc shift [x/y/z/pitch/yaw] [amount] | Shifts the currently held location's specified axis by a certain amount.
/loc shift [x] [y] [z] [pitch] [yaw] | Shifts the currently held location's specified axis to a certain value.
/loc set [x/y/z/pitch/yaw] [value] | Sets the currently held location's specified axis to a certain value.
/loc set [x] [y] [z] [pitch] [yaw] | Sets the currently held location's specified axes.

## NBT Format

`{"id":"loc","data":{"isBlock":false,"loc":{"x":0,"y":0,"z":0,"pitch":0,"yaw":0}}}`

- "loc" represents the location that the item is set to.
- "isBlock" is currently unused.