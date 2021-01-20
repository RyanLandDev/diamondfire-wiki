# Text Codes

Text Codes may be confusing at first, but once you know how they work, they can be extremely useful!

Essentially text codes change the *name* of a variable, making it dynamic. It changes the *name*, not the *value*.

For example, say we have a variable called **%default money**. The variable you're using here is actually **RyanLand money**, because that's the *name* of the default target.

All text codes can also be nested inside of eachother.

See also: [Event Targets](Other/Code_Related/Event_Targets.md)

Here's a list of all available text codes and their explanations (alphabetically):

Text Code | Description
--- | ---
%damager | The name of the damager target in this event. Only works in damage events.
%default | The name of the default target in this event, the player or entity running the code.
%index(list variable name, index) | Gets the value from the [list](Variables/List.md) from the index provided. Example:
list = [ a, b, c ]
ad = 100
%index(list,1)d returns 100
%killer | The name of the killer target in this event. Only works with kill events.
%math(expression) | Returns the output of a mathematical expression. Note that this is for numbers. Texts behave differently.
Does not follow PEMDAS/OoO, also does not support parenthesis (use nested %math). Supports the following operations:
- Sum (+)
- Difference (-)
- Product (*)
- Quotient (/)
- Remainder (%)
Example: **%math(5+3*2)** gives 16 and not 11. **%math(5+%math(3*2))** does give 11.
%projectile | The name of the projectile in this event. Only works with projectile events.
%random(min, max) | Gives a random number with a rounding multiple of 1 between and including the minimum and maximum.
%round(number) | Floors the given value (text code name is false). To round to nearest or ceil, use [Set Variable: Round Number](Code_Blocks/Set_Variable/Round_Number.md)
%selected | The name of the selected object. To clear up confusion: Multiple objects being selected will run code for every object in the selection for specific code blocks, **%selected** would return the name of the object running the code, which is different for every object when using selections bigger than one. Please see [Event Targets](Other/Code_Related/Event_Targets.md) and [Select Object](Code_Blocks/Select_Object.md).
%shooter | The shooter of the projectile in this event. Only works with projectile events if the projectile was launched by a player or entity (including have used [Entity](Code_Blocks/Entity_Action/Launch_Projectile.md) or [Player Action: Launch Projectile](Code_Blocks/Player_Action/Launch_Projectile.md)). Also applies to other entities.
%uuid | Identical to **%selected**, but instead, gets the [UUID](Other/Code_Related/UUID.md) instead of the name. A UUID is unique to every player account and entity.
%var(variable name) | Returns the value of the [variable](Variables.md). Example:
a = 1
1b = 2
%var(a)b returns 2
%victim | The name of the victim in this event. Only works in damage events.
