# Example Project for the Unreal Engine Camera Capture Plugin

Example project showing the use of the [Camera Capture Plugin for Unreal
Engine 5](https://github.com/finger563/unreal-camera-capture)

![image](https://github.com/finger563/unreal-camera-capture-example/assets/213467/eec72979-80be-4d82-9377-1977e681f960)

Provides:
- A set of input actions (Look, Move, Capture, Serialize) which are used by the
  `BP_CapturePawn` for controlling it.
- A `BP_CapturePawn` pawn class which contains a single camera (front). It has a
  single camera (`front`) and is configured to capture data every 0.5 seconds.
  It also has a small sphere collider so that it will not clip through objects.
  It auto-possesses player 0 and supports the following inputs:
  - `wasd`: Standard FPS movement for a floating pawn (e.g. motion along the
    look vector, strafing along the right vector)
  - `mouse`: Standard captured FPS mouse look (pitch and yaw) for a floating
    pawn.
  - `spacebar`: Toggle capturing data. Capturing is initially enabled when
    starting to play.
  - `f`: Toggle writing captured data to files (serialization). Serialization is
    initially disabled when starting to play.
- A `CaptureMap` which has a scene set up together with a `BP_CapturePawn`. This
  is the default map which will load when you load the project. Pressing play to
  play in this level will auto-possess the `BP_CapturePawn` and start capturing.


## Usage

Run the example map in the editor. If you want to change the settings, simply
select the `BP_CapturePawn` in the scene hierarchy and then select its `Capture`
component. Within there you can configure:

- `Timer Period`: if 0, will capture every frame, if non-zero it will capture
  according to the period you configure, in seconds.
- `Timer Delay`: If non-zero, will add a wait before the first capture.
- `Capture Source`: Should be `Final Color (LDR) in RGB`, but you can change it
  to whatever you want.
- `Hidden Actors`: List of actors in the scene which should not be captured.
  Used to not capture certain actors. Set
- `Image Width`: The width of the images that will be saved
- `Image Height`: The height of the images that will be saved
- `Save Location`: optional path to store output files. If empty (default), it
  will save in the root of the project in the folder `camera_data`.

The following properties are visible, but should not be configured as they are
automatically configured when running the game:
- `Dmv Cameras`
- `Rgb Cameras`
- `Dmv Textures`
- `Rgb Textures`

### Controls

Capture/serialization:
- `Space`: Start/Stop capturing. Capturing starts on begin play by default.
- `f`: Start/Stop serialization. Serialization is stopped on begin play by default.

Movement:
- `wasd`: movement
- `mouse`: look
