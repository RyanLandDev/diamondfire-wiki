# Lagslayer

Lagslayer is the system in DiamondFire to prevent a plot from causing too much lag on the server.

## Ways to trigger
- Plot is taking up too much CPU. (Halts all code on the plot)
- Loop halted for fast looping. (Triggered if code is being looped over 10 times without a Control.Wait)
- Plot exceeded event/process nesting limit. (An event/process that triggers an event/process 90 times within itself)
- Wait limit exceeded. (Five-thousand waits or more running at the same time)
- Variable limit exceeded. (Five-hundred-thousand or more GAME or SAVE variables created.)

## CPU
The plot's CPU is something you always need to keep in mind when coding a plot. You can see your plot's cpu by typing /lagslayer. It is a value between 0% and 100% of the plot's max cpu and is updated every 20 ticks of the server. Every time the CPU value updates, or a CPU-intensive action is being executed, the CPU is checked. If the CPU value is greater than 100%, then the plot is halted for an X amount of time, depending on how badly the CPU went over.

## CPU-Intensive Actions

A CPU-intensive action is one that checks to see if the plot has gone over 100% CPU.

`Set Variable -> List -> Append Value`  
`Set Variable -> List -> Append List`  
`Set Variable -> List -> Insert Value at Index`  
`Set Variable -> List -> Sort List`  
`Set Variable -> List -> Randomize List`  
`Set Variable -> List -> Reverse List`  
`Set Variable -> List -> Remove List Index`  
`Set Variable -> List -> Remove List Value`  
`Set Variable -> Purge Variables`  

`Game Action -> Block Manipulation -> Bone Meal Block`  
`Game Action -> Block Manipulation -> Random Tick Block`  
`Game Action -> Block Manipulation -> Set Block`  
`Game Action -> Block Manipulation -> Break Block`  
`Game Action -> Entity Spawning -> Launch Projectile`  
`Game Action -> Entity Spawning -> Spawn Item`  
`Game Action -> Entity Spawning -> Spawn Random Item`  
`Game Action -> Entity Spawning -> Spawn Mob`  
`Game Action -> Entity Spawning -> Spawn Vehicle`  

`Player Action -> Projectiles -> Launch Projectile`  
`Player Action -> Item Management -> Save Inventory`  
`Player Action -> Item Management -> Load Saved Inventory`  

`Entity Action -> Miscellaneous -> Launch Projectile`  