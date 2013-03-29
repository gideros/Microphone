Microphone plugin for Gideros
=============================

Use this plugin to record to an audio clip using a connected microphone.

## Reference

`Microphone.new(deviceName, sampleRate, numChannels, bitsPerSample)`
Creates a new Microphone object. 

**deviceName - (string)**: The name of the device. Passing nil or an empty string will pick the default device.
**sampleRate - (number)**: Sample rate of the recording. This value should be between 4000 and 44100.
**numChannels - (number)**: Number of channels. This value can be 1 for mono and 2 for stereo.
**bitsPerSample - (number)**: Bits per sample. This value can be 8 or 16. 

----
`Microphone:setOutputFile(fileName)`
Sets the output file. If an output file is specified, captured audio is recorted to this file. You cannot set output file while recording.

**fileName - (string)**: The filename. It should be on documentes or temporary directory.

----

`Microphone:start()`
Start recording with device.

----

`Microphone:stop()`

Stop recording.

----

## Events
`Event.DATA_AVAILABLE`
Dispatched as audio samples become available.
**event.peakAmplitute**: The audio channel's peak amplitute.
**event.averageAmplitute**: The audio channel's average RMS amplitute.

----

## Installation
### Windows
Copy bin/microphone.dll to Plugins directory.
### Mac OS X
Copy bin/microphone.dylib to Plugins directory.
### iOS
Add `gmicrophone-ios.mm`, `gsoundencoder-wav.cpp` and `gmicrophonebinder.cpp` to Xcode project.
### Android
Copy bin/Android/* to libs directory.
Copy source/com/* to your project.
Add `System.loadLibrary("microphone");` to your main Activity.
Add `"com.giderosmobile.android.plugins.GMicrophone"` to `externalClasses` array.
Add `android.permission.RECORD_AUDIO` permission.


## Notes
Most android devices doesn't support 8-bit recording.

