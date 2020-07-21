# Console command for CS:GO

Console needs to be enabled in options. Most commands need the sv_cheats option to be enabled on the server. This can be achieved by starting a local training match with bots, followed by typing `sv_cheats 1` in the console.

## Generally helpful commands
- `mp_roundtime 60` sets round time to maximum of 60 minutes to avoid round restart during demo.
- `mp_restartgame 1` restarts the round after 1 second, resetting the round timer.
- If a bot is needed for anything, you can place a static one using `bot_stop 1`, `bot_add`, `bot_place`.
- `noclip` toggles noclip mode.
- `find` searches all commands.

## Rendering and culling
Note: Leaving palace on Mirage towards A is a good location for visualizing culling.
- `r_DrawPortals 1` visualizes the portals used for culling, both aligned to the geometry as well as screen aligned. Portals are marked as active if they intersect any of the current room's portals in screen space.
- `mat_wireframe 1/2/3` implements three wireframe drawing modes, `3` seems to be a good choice for culling demos, as only big geometries such as walls are rendered, resulting in a less cluttered scene.
- `r_portalsopenall 1` forces all portals to be marked active.
- `r_lockpvs 1` locks the potentially visible set. Note that this does not lock everything, but the idea can be conveyed.
- `r_novis 1` disables the PVS. This should be used in combination `mat_wireframe 1`, resulting in lots of smaller models being rendered.
- `r_drawviewmodel 0` can be used to hide your weapon.

## Other useful commands
- `mat_postprocess_enable 0` disables post processing. There are no strong effects in CS:GO, only antialiasing and slight darkening in the screen's corners.
- `mat_showmiplevels 1` draw the currently active mip map levels.
- `r_depthoverlay 1` draws the depth buffer.
- `mat_reversedepth` inverts the depth buffer.
- `create_flashlight` spawns a flashlight using projection mapping at the current view position. The flashlight is static, allowing to show that hidden areas are lit up. `r_flashlightbrightness 1` can be used to make it brighter. The other `r_flashlight[...]` commands don't seem to do anything.
- `r_farz` sets the far plane for level rendering (skybox will still be drawn).
- `mat_normalmaps 1` draw the normal maps of big surfaces.
- `mat_show_histogram 1` shows a histogram for the current frame in the top-right corner.
- `+showvprof` opens a interactive overview of frame time composition. Disable using `-showvprof`.
- `fov_cs_debug` overrides the FOV with a given value.
- `sv_showlagcompensation 1` draws hitboxes when shooting. `sv_showlagcompensation_duration` can be used do keep them around for longer.
- `sv_showimpacts 1` shows bullet penetration enter and exit points.
- `mat_ambient_light_r` (or g, b) can be used to add ambient lighting.
