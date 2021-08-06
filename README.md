# TensorFlow Lite Object Detection iOS Example Application

This repo is a copy of the TensorFlow Object Detection Example for Swift from [here](https://github.com/tensorflow/examples/tree/master/lite/examples/object_detection/ios)

Follow that README.md for detailedinstallation and setup instructions.

The main focus of this repo is to compare two models for performance differences.


For your convenience, the two .tflite models are included in the repo. You do not need to download anything externally.

The two models are:
1. mobilenet_toco.tflite 
2. vertex_mlir.tflite , a sample object detection model generated from Vertex AI using Google AutoML Vision.

There are small differences between the models:

| Model   |      Input      |  Converted Via | TF Runtime | Quantized? | Notes |
|----------|:-------------:|------:|------:|------:|------:|
| mobilenet_toco |  300x300x3 | TOCO | 1.15 | Yes | standard model pulled from [here](https://storage.googleapis.com/download.tensorflow.org/models/tflite/coco_ssd_mobilenet_v1_1.0_quant_2018_06_29.zip) |
| vertex_mlir |    320x320x3   |   MLIR |   2.5 | Yes | sample model generated & exported using Google AutoML Vision |
 