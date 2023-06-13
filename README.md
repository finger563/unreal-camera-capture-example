# Example Project for the Unreal Engine Camera Capture Plugin

Example project showing the use of the [Camera Capture Plugin for Unreal
Engine 5](https://github.com/finger563/unreal-camera-capture)

![image](https://github.com/finger563/unreal-camera-capture-example/assets/213467/eec72979-80be-4d82-9377-1977e681f960)

Provides:
- A set of input actions (Look, Move, Capture, Serialize) which are used by the
  `BP_CapturePawn` for controlling it.
- A `BP_CapturePawn` pawn class which contains a single camera (front). It has a
  single camera (`front`) and is configured to capture data every 0.5 seconds.
  It auto-possesses player 0 and supports the following inputs:
  - `wasd`: Standard FPS movement for a floating pawn (e.g. motion along the
    look vector, strafing along the right vector)
  - `spacebar`: Toggle capturing data. Capturing is initially enabled when
    starting to play.
  - `f`: Toggle writing captured data to files (serialization). Serialization is
    initially disabled when starting to play.
- A `CaptureMap` which has a scene set up together with a `BP_CapturePawn`. This
  is the default map which will load when you load the project. Pressing play to
  play in this level will auto-possess the `BP_CapturePawn` and start capturing.
