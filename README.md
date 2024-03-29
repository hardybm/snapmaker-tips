# snapmaker-tips

```
;Auto Level
G1029 P11 ;11x11 grid
G1029 A ;start leveling

G91; relative positioning for Z offset move

G0 Z-XXX; now leveling sampling is done, move the head to a Z offset you want, then save

G1029 S ;save data

G1029 D0 ;end leveling

G0 Z10; move up 10mm
G90; restore absolute positioning
```


IF you need to adjust the Z height later (say switching to a shorter nozzle)
```
G1029 D0.05; after leveling raise the level 0.05 
```


Reference https://snapmaker.github.io/Documentation/gcode/G1029-abl

## using lightburn and snapmaker

There are two main ways to use the snapmaker laser engraver.
1) A big sheet referenced against the front left corner
1) An existing item that needs precise positioning

###A big sheet referenced against the front left corner (absolute positioning)
- Set lightburn to absolute coordinates
- Send the job to the snapmaker 
- on the snapmaker set the origin to the bottom left corner (instead of the center where it starts)

###An existing item that needs precise positioning
- in Lightburn->Edit->Settings->'Ignore out-of-bounds shapes if possible' - SET OFF
- set Lightburn to current position and set the refence point (center or bottom left or whatever)
- set the work origin to the matching point on what you want to burn of where you want the burn
- run boundary works
