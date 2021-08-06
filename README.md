# TensorFlow Lite Object Detection iOS Example Application

This repo is a copy of the TensorFlow Object Detection Example for Swift from [here](https://github.com/tensorflow/examples/tree/master/lite/examples/object_detection/ios)

Follow that README.md for detailed installation and setup instructions.

**Quick Start**
1. Run `pod install` to install TensorFlow Lite pods
2. Open the .xcworkspace file in Xcode (NOT the .xcodeproj file) and make sure the model files exist in Model/models. 
    If they do not exist or are red, just drag the files into Xcode from the models/ directory
3. Change your Team in the Xcode Project -> Targets -> Signing & Capabilities
4. Select which model you want to use on Line 40 of ModelDataHandler.swift. Default is vertex_mlir (the model that has an issue using CoreML Delegate)
5. Run on Device!

**Purpose**

The main focus of this repo is to compare two models for performance differences.

For your convenience, the two .tflite models are included in the repo. You do not need to download anything externally.

The two models are:
1. mobilenet.tflite 
2. vertex_mlir.tflite 

There are small differences between the models:

| Model   |      Input      |  Converted Via | Quantized? |
|----------|:-------------:|------:|------:|
| mobilenet |  300x300x3 | TOCO | Yes | standard model pulled from  |
| vertex_mlir |    320x320x3   |   MLIR |  Yes |
 

**Error**

Loading vertex_mlir.tflite results in a CoreML error

```
ObjectDetection[50052:5356650] Failed to Compile and save Model.
ERROR: Failed to Compile and save Model.

ObjectDetection[50052:5356650] Error compiling model Error reading protobuf spec. validator error: Padding type for the pooling layer 'PoolingLayerBuilder (MEAN)_1' is not set.
```
