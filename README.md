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
