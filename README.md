# Workshop: Feedback

Workshop early access resources.

See [Instructions](https://github.com/bgulanowski/workshop-feedback/wiki/Instructions) for an intro.

This repo is meant for public issue tracking and wiki content. We don't expect to host any source files here.

## Download

**NOTE: 0.1.19 has been updated to build c **

[V 0.1.19c (alpha)](https://github.com/bgulanowski/workshop-feedback/releases/download/v0.1.19c-alpha/Workshop.v0.1.19c-alpha.app.zip)

## Samples

See the Samples folder for a couple of files to download.

![Scotia Plaza Tower](https://github.com/bgulanowski/workshop-feedback/blob/master/Workshop%20-%20Scotia%20Plaza%20(partial).png "Scotia Plaza Tower")

## Change log


### Changes: 0.1.19

**New features**

- New "wall" tool: generate filled rhomboids by extruding a path in a given direction
- support for resizing the window in windowed mode
- option-double-right-click to automatically move camera to a point

**Bug fixes**
- CMD-R activates the Region Selection tool
- ESC switches back to Cell tool
- restore working items in the main menu panel
- prevent the main menu panel from appearing and getting stuck after showing help
- CMD-X (Cut command) once again deletes cells as well as copying them
- fix missing objects in the object palette (aka the "materials palette", as distinct from the colours palette)
- improve the help panel to make it more readable
- prevent baize (platform) disappearing
- fixes for quick delete with cell tool

**Known issues**
- help is incomplete

**other changes**
- under the surface a lot of code was refactored and optimized, reducing code size

### Changes: 0.1.18

**Bug fixes**
- Restore support for screenshots with F2 (may require holding Fn key)
- Prevent exceptions caused by trying to draw non-existent chunks
- Fix issue with contents of a closed file appearing in next one opened
- Fix issue with selection extension in Region Selection tool
- Fix issue with current tool changing unexpectedly
- Fix issue with Brush tool being incorrectly disabled
- Fix a crash when drawing a line that is only 1 cell in length
- Fix bug when canceling selected point using Line Segments tool
- Fix crash when activating Tool popup
- Fix accidental deletions when using Region Selection tool

**Enhancements**
- New tools: Triangle-outline; Triangle-filled; Line Segments
- New icons for all tools

**Other**
- Lots of unit tests; still need more
- Upgrade to use Unity 2020 (formerly Unity 2018)
- Reduce binary size by removed obsolete assets
- Tweaks to how sky is drawn, lighting, and other minor changes

### Changes: 0.1.17

**Bug fixes**
- Prevent text typed into UI from being interpreted as commands
- Fix a problem with image generation in the Brushes panel
- Fix issue with selection being ignored on copy
- Prevent a crash on startup

**Enhancements**
- Revised Tool Bar 
- Improve the colour palette

**Optimization**
- Generate parcels concurrently; a parcel is a 3D model representing a chunk (a 16x16x16 group of cells)
- Reduce memory allocations for frequently used code

**Notes**
- There was no version 0.1.16
- 0.1.17 was never released officially
- Both versions 0.1.17 and 0.1.18 saw a dramatic amount of code rewriting ("refactoring") to improve code structure and organization, to reduce the chance of bugs, and to make new features easier to implement.
 
### 0.1.15

Camera movement improvements, and brush library.

Orbiting and zooming now work relative to the selection indicator. This feels more intuitive, and makes navigation much faster, since you can choose exactly where your movements are in relation to.

The Brush Library lets you save and load copied regions of cells. Make a small model, copy it, and save it for later. Save as many brushes as you like.

A few small fixes, like use of Cntl key to simulate right mouse button.

This should be the last release in the 0.1 alpha line. 0.2 will start introducing more dramatic features.

### 0.1.14

Performance improvements and bug fixes.

**Performance:**
- Improve mesh generation speed with early loop termination
- Generate more chunk meshes each frame (tweak change from 0.1.13b)
- Avoid creating new chunks when copying regions
- Avoid creating new chunks when erasing regions
- Delete empty chunks when saving
- When loading a document, verify chunks have non-empty data

**Fixes:**
- Finish region selection on second click when third click not needed
- Ensure buffer preview is generated even when hidden
- Delete a cell even if it's on a different layer than the active layer
- Restore ability to cancel Region Selection mode with Escape key
- Ensure buffer transforms are correctly reset when copying a region
- Use the correct cell layer as mask when clearing before copying
- Ensure buttons in popovers are scaled to match other UI
- Enlarge images to reduce jaggy appearance in scaled buttons
- Use correct colour when selecting colour from colour palette
- Prevent changing colour selection to invalid values during app launch

### 0.1.13

This release implements another batch of improvements to editing.

When pasting a block of cells from the paste buffer, there are three new controls:
 - rotate around Y axis (vertical) with '[' and ']' (square brackets), or Z axis (forward) if holding shift
 - mirror across X axis (left/right) with '\' (backslash), or Y axis if holding shift
 - show a widget at the pivot point to make it clear where the pasted cells with be placed
 - toggle pivot point across edges to move to different corners of the selection box (1, 2, 3 keys)
 - colour the selection box according to the selection status (see below)
 - don't overwrite filled cells with empty cells from the paste buffer
 - copy a coloured cell's substance in the same way as a textured one (CMD-C)
 - a couple of minor fixes

Rotation works in either of two ways: doorknob and sink faucet. Doorknob rotation works around the front/back axis closest to the direction of the camera. Faucet rotation always works around the vertical axis.

Mirroring also works in two ways, but not as intuitive. The first way is akin to the relationship of two halves of an archway when viewing through the arch: left <-> right. The second way is akin to how the background reflects in a lake surface, above <-> below.

Rotation around the forward axis, and mirroring in in the left/right direction, are performed relative to the camera.

Moving the pivot point is a more complex action. It provides a work around to some problems trying to place buffer blocks beside existing cells.

Rotation, mirroring, and pivot point adjustment are all non-destructive actions, but they are remembered until the paste buffer is replaced by performing another block copy operation.

### 0.1.12
- support for extending a region selection from 2d into 3d
- fix more UI scaling issues

### 0.1.11
- rotation of buffer blocks when pasting
- fix issues when copying blocks when the camera is rotated
- fix issues with UI layout at different resolutions

### 0.1.10

First release here. Features:
- cell editing in 3d space: fill/clear individual or blocks of cells
- textured substances
- solid colour substances
- preliminary copy and paste
- document save and load
