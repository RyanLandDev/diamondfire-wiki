# Game Value

Game values are variables that contain a value relating to something within the plot. These can relate to something like a specific player's inventory items, the plot's CPU usage, or the location of an event block.

These values cannot be edited directly. You need to set them to a variable to then edit the value.

Game values are split into six categories: Statistics, Locations, Items, Informational, Events, and Plot.

## NBT Format

`{"id":"g_val","data":{"type":"Location","target":"Default"}}`
- "type" is the current game value that the item has selected.
- "target" represents the current target the item has selected. *Note that even (No target) selectors are set to default*