## Release notes for Unity SDK

### Version 0.5.0 - 2019/11/16

**Features**
- Streaming support to record full gameplay sessions
- Added utility script for automatically setting UI canvas to camera space

**Improvements**
- Use microseconds to define event time
- Better session events synchronization
- Improved API security

**Bug Fixes**
- Fix ftux events in live mode

### Version 0.4.4 - 2019/06/12

**Features**
- Added ability to add custom data to any event

**Improvements**
- Event's data changed to `object`, so anything that can be serialized will be included with event
- Stop recording when backend quota is reached

**Bug Fixes**
- Reset input data on each new event
- Prevent events from using the same capsule id

### Version 0.4.0 - 2019/04/09

**Features**
- Backend API will now inform SDK which events to capture
- Removed function `SendCapsule` as capsules will be send according to events of interest
- Added ability to record capsule before, after or around events

**Improvements**
- Better handling of pause event in Unity Editor

**Bug Fixes**
- Fix capsule frame rate to 30fps (this is for inputs and metadata, image fps is controlled by backend)

### Version 0.3.0 - 2019/03/19

**Features**
- Record session information in the form of events
- Created `AddEvent` function to add custom events including data

**Improvements**
- First time an event is detected in live mode, it will be tagged as ftux
- Add option to stop recording based on CPU usage
- Optimizations for recording screen

**Bug Fixes**
- Don't reset settings when upgrading SDK
- Default to 30 fps if `Application.targetFrameRate` is not set
- Clear cache when settings change to not save capsule on disk

### Version 0.2.2 - 2019/02/18

**Improvements**
- Remove automatic rob0 popup asking to enter device name

### Version 0.2.1 - 2019/02/05

**Bug Fixes**
- Change default settings

### Version 0.2.0 - 2019/01/23

**Features**
- Capsule player included in SDK

**Improvements**
- Simulate application minimize when Editor is paused

## Known issues

* In order for the recording to work, all UI Canvas need to render to a camera.
* In order to capture screenshots without impacting performance we use `Rendering.AsyncGPUReadback` which is only available in Unity 2018.1 for Android using the Vulkan graphics API and Unity 2018.3 for iOS. If you're unable to use the latest versions of Unity you may experience a slight performance impact on older devices.
* Since iOS interrupts all web requests once the app is minimized, you'll need to manually trigger an upload using `Rob0.Rob0Controller.SendCapsule("your-custom-event-name");`. We're currently working on a solution that would use background tasks.
