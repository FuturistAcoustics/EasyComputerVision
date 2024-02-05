<p align="center">
  <a href="https://assetstore.unity.com/packages/tools/ai-ml-integration/easy-computer-vision-261410"><img src="https://github.com/FuturistAcoustics/EasyComputerVision/blob/main/Images/EasyComputerVision%20Logo%20192x192.png"></a>
</p>
<p align="center">
  <a href="https://futuristacoustics.com/"><img src="https://futuristacoustics.com/wp-content/uploads/2023/09/Futurist-Acoustics-Logo-Favicon.png" width=26px></a>
  <a href="https://www.linkedin.com/company/futurist-acoustics/"><img src="https://futuristacoustics.com/wp-content/uploads/2023/10/LinkedIn-2023.svg" width=28px></a>
  <a href="https://www.youtube.com/@futuristacoustics"><img src="https://futuristacoustics.com/wp-content/uploads/2023/10/YouTube-SM.svg" width=28px></a>
  <a href="https://www.reddit.com/r/FuturistAcoustics/"><img src="https://futuristacoustics.com/wp-content/uploads/2023/10/Reddit-2023.svg" width=28px></a>
  <a href="https://twitter.com/FutAcoustics"><img src="https://futuristacoustics.com/wp-content/uploads/2023/10/X-2023.svg" width=28px></a>
  <a href="https://github.com/FuturistAcoustics"><img src="https://futuristacoustics.com/wp-content/uploads/2023/10/GitHub-SM.svg" width=28px></a>
</p>

# EasyComputerVision
## Object Detection Tutorial
This tutorial details how to use the demo project included in EasyComputerVision, which involves using an in-game camera as input to a neural network for object detection and viewing the output.

We recommend you try the [image classification tutorial]() first, as this tutorial expands on some EasyComputerVision concepts.

### 1. Project Setup
Create and save an empty 3D Unity project. EasyComputerVision requires the Sentis package. An easy way to add Sentis is to go to Window > Package Manager > + > Add package by name, then paste in `com.unity.sentis` in the Name field and select Add.

Next, open a project. In Unity go to "Window" > "Packet Manager". In the Packet Manager that opens, change "Packages:" to "Packages: My Assets". Select EasyComputerVision, then Download, then Import. The import will appear in the project window.

<!-- ![alt text](https://github.com/FuturistAcoustics/EasyComputerVision/blob/main/Images/Tutorial%201.1.0/Image%2001.png "Tutorial_1") -->

### 2. Opening the Demo Scene
Open the demo scene by going to Futurist Acoustics > EasyComputerVision > Demo > ObjectDetection > ObjectDetection. You will see two objects that contain an image of a bird and a dog and a camera object positioned to face it.

<!-- ![alt text](https://github.com/FuturistAcoustics/EasyComputerVision/blob/main/Images/Tutorial%201.1.0/Image%2002.png "Tutorial_2") -->

### 3. Importing a Model
We have included the YOLOv7 Tiny ONNX model for you and the corresponding labels.

<!-- ![alt text](https://github.com/FuturistAcoustics/EasyComputerVision/blob/main/Images/Tutorial%201.1.0/Image%2003.png "Tutorial_3") -->

### 4. Setup
Select the EasyComputerVision game object. This object contains the EasyCVObjectDetection script component.

<!-- ![alt text](https://github.com/FuturistAcoustics/EasyComputerVision/blob/main/Images/Tutorial%201.1.0/Image%2004.png "Tutorial_4") -->

As you can see, the ONNX model has already been defined. Also, the in-game camera has already been set as the input camera. This is used as the input to our model. The Auto Create Input Texture boolean is also set to true because the camera input must be passed to a render texture before being input to the model. Auto Create Input Texture removes this intermediary step. It gets the model input dimensions to create the render texture and will automatically fill in the Input Texture field on run. You can create your own render texture if you'd like, just leave this boolean unticked and drag your render texture into the Input Texture field in order to do this. For object detection, you must include labels, and this has been already done for you.

We also allow different ways to run inference under Inference Type. We recommend using either of the Scheduled Execution inference options for less computationally intense inference. If you're using one of the On Key Press options, you can define the key in the Key drop down. By default this is the letter 'I' (for inference).

For this demo, set the Inference Type to Keypress so that when you press 'I' then inference will run.

Ensure View Output is set to true to view the output of the model. You can modify it's X and Y positions and its scale.

Setting View Input to true under Helper allows you to view the input texture that is input to the model as a canvas. You can adjust the size and position of the canvas' image by adjusting the X Position, Y Position, and Scale.

### 5. Inference
Run the game and press 'I' to run inference. You will see the two animals with bounding boxes in the game view.

<!-- ![alt text](https://github.com/FuturistAcoustics/EasyComputerVision/blob/main/Images/Tutorial%201.1.0/Image%2005.png "Tutorial_5") -->

### 6. Appendix
You can also use the webcam as input by setting Use Webcam to true in the Input section.

Under Engine Type, the backend can be set. By default, we use the most GPU efficient engine. More can be learnt about the options by hovering your mouse over this field or at the [Sentis docs](https://docs.unity3d.com/Packages/com.unity.sentis@1.2/manual/create-an-engine.html?q=worker).

-----

EasyComputerVision is created by [Futurist Acoustics](https://futuristacoustics.com/) <a href="https://futuristacoustics.com/"><img src="https://futuristacoustics.com/wp-content/uploads/2022/12/Media-Asset-Logo-1024%E2%80%8A%C3%97%E2%80%8A1130-928x1024.png" width=14px></a>.

[Purchase EasyComputerVision on the Unity Asset Store](https://u3d.as/37DT) <a href="https://u3d.as/37DT"><img src="https://github.com/FuturistAcoustics/EasyComputerVision/raw/main/Images/EasyComputerVision%20Logo%20192x192.png" width=14px></a>