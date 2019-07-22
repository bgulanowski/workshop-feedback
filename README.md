# workshop-feedback

Workshop early access resources.

See [Instructions](https://github.com/bgulanowski/workshop-feedback/wiki/Instructions) for an intro.

This repo is meant for public issue tracking and wiki content. We don't expect to host any source files here.

## Download

[V 0.1.13 (alpha)](https://github.com/bgulanowski/workshop-feedback/releases/download/v0.1.13-alpha/Workshop.v0.1.13-alpha.app.zip)

## Change log

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
