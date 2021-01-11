# Event Targets

Targets are used to represent select a player, mob, or entity. These are useful for doing general actions such as sending a message to all players or putting the player's name in the chat. [Player Action](Code_Blocks/Player_Action.md), [If Player](Code_Blocks/If_Player.md), [Entity Action](Code_Blocks/Entity_Action.md), and [If Entity](Code_Blocks/If_Entity.md) all accept targets. The [Set Variable](Code_Blocks/Set_Variable.md) codeblock runs on the selection target, performing the operation once per selected object, as well as certain actions such as [Repeat: While](Code_Blocks/Repeat/While.md) and certain [Select Object](Code_Blocks/Select_Object.md) actions. [Game Action](Code_Blocks/Game_Action.md), [If Game](Code_Blocks/If_Game.md), and [Control](Code_Blocks/Control.md) are **target independent**, meaning how they operate is not affected in any way by targets. For example, a [Game Action: Set Block](Code_Blocks/Game_Action/Set_Block.md) will not run for every selected player, instead only running for one.

## Target Types

Each target is split into a specific type: player, mob, or entity. Note that entity targets are compatible with mob targets, but not necessarily the other way around. When a target is requested, DiamondFire will check if the target exists, and if so, it will check that it is of the correct type.

For example: when an [Entity Action](Code_Blocks/Entity_Action.md) on the [Kill Mob Player Event](Code_Blocks/Player_Event/Kill_Mob.md) requests the default target, DiamondFire will see that this target is actually a player target, and will attempt to select the victim target instead.

## Target Priorities

Each target may be substituted for another if not present. For example, `%default` may represent `%killer` if no default target was passed in the event.

Target Name | Checked Targets
--- | ---
Default | Default, Killer, Damager, Shooter, Victim Projectile
Killer | Killer
Damager | Damager, Killer, Shooter
Shooter | Shooter
Victim | Victim
Projectile | Projectile

## Action Targets

Action targets allow for specification of whom is affected by code, such as which player or entity a game value targets, or whom a player action affects. For example, you can send a message to each player on the plot using the `All Players` target.

Target | Description
--- | ---
Current Selection | Targets everything selected, falling back to the default target if nothing is selected.
Default | Targets the player or entity that triggered the event.
Killer | Targets the killer in a death-related event.
Damager | Targets the damager in a damage-related event.
Shooter | Targets the player or entity that shot the projectile involved in the event.
Victim | Targets the player or entity harmed in a damage- or death-related event.
**Entity Only** |
All Entities | Targets all entities, excluding players, on the plot.
All Mobs | Targets all mobs on the plot (e.g. zombies, creepers, etc.), but not other entities.
Projectile | Targets the projectile involved in the event.
Last Mob Spawned | Targets the most recently spawned mob on the plot.
Last Entity Spawned | Targets the most recently spawned entity on the plot, excluding players.
**Player Only** |
All Players | Targets all players on the plot.

Certain code blocks accept action targets, while others do not, while still others use a default action target, or no action target at all. Code blocks that support configurable action targets through shift + right-clicking the code block are the [Player Action](Code_Blocks/Player_Action.md), the [If Player](Code_Blocks/If_Player.md), the [Entity Action](Code_Blocks/Entity_Action.md), and the [If Entity](Code_Blocks/If_Entity.md) blocks. The [Set Variable](Code_Blocks/Set_Variable.md) block has the Current Selection target as its default target, and so does the [Repeat](Code_Blocks/Repeat) block if it is set to the [Repeat: While](Code_Blocks/Repeat/While.md) action. This also applies to any [Select Object](Code_Blocks/Select_Object.md) actions that require an additional condition, such as the [Select Object: Players By Condition](Code_Blocks/Select_Object/Players_By_Condition) action, and the same goes for the [Process](Code_Blocks/Process) block if it is set to run for each target in the selection.

Blocks that do not have any target, and are therefore never affected by selections, are the [If Variable](Code_Blocks/If_Variable.md) block, the [Game Action](Code_Blocks/Game_Action.md) block, the [If Game](Code_Blocks/If_Game.md) block the [Call Function](Code_Blocks/Call_Function.md) block, the [Control](Code_Blocks/Control.md) block, and the [Repeat](Code_Blocks/Repeat.md), [Select Object](Code_Blocks/Select_Object.md), and [Process](Code_Blocks/Process.md) blocks for the actions or tag options not mentioned above. This list does not include line starter blocks.

## Text Targets

Text targets are pieces of text that represent a specific target, and are substituted for the target's respective name or [UUID](Other/Code_Related/UUID.md). For example, `%default` on [Player Event: Join Game](Code_Blocks/Player_Event/Join_Game.md) will be replaced with the name of the player who joined the plot. Text targets are to be used on variable items which accept a name value. If an action uses the Current Selection target and a selection is currently active.

`%selected`, is used in conjunction with the selection target, where they both represent the players or entities selected through [Select Object](Code_Blocks/Select_Object.md). The selection target will perform an action on the selection, while the previously mentioned text codes will give the selection's name(s).

*Text targets do not actually select players or entities.*

Target | Compatible Types | Description
--- | --- | ---
%default | All | The name of the player, mob or entity who executed the event.
%selected | All | The name of the currently selected target, falling back to the default target if nothing is selected. Intended to be used with actions set to the current selection target. Using this in conjunction with the `Default` action target will represent either `%default`, or the 1st player or entity selected.
%uuid | All | Behaves exactly as `%selected` does, but returns a [UUID](Other/Code_Related/UUID.md) rather than a name.
%killer | Players, mobs | The name of the player or mob who killed `%victim`.
%damager | Players, mobs | The name of the player or mob who damaged `%victim`.
%victim | Players, mobs | The name of the player or mob who was damaged or killed.
%shooter | Players, mobs | The name of the player or mob who shot the projectile in the event.
%projectile | Entities | The name of the projectile involved in a projectile-related event.