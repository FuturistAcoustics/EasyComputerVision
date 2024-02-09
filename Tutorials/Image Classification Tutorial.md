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
## Image Classification Tutorial
This tutorial details how to use the demo project included in EasyComputerVision, which involves using an in-game camera as input to a neural network for image classification and viewing the output.

### 1. Project Setup
Open or create a 3D Unity project. After purchasing EasyComputerVision, go to "Window" > "Packet Manager". In the Packet Manager that opens, change "Packages:" to "Packages: My Assets". Select EasyComputerVision, then Download, then Import.

The Sentis package is a dependency to EasyComputerVision, so should already be installed when you import the package. If you see errors because Sentis isn't installed, an easy way to add Sentis is to go to Window > Package Manager > + > Add package by name, then paste in `com.unity.sentis` in the Name field and select Add.

<div align="center">
  <a href="Images\Image Classification Tutorial\Image 01.png" target="_blank">
    <img src="Images\Image Classification Tutorial\Image 01.png"/>
  </a>
</div>

### 2. Opening the Demo Scene
Open the demo scene by going to Futurist Acoustics > EasyComputerVision > Demo > ImageClassification > ImageClassification. You will see a plane with an image of a bird on it and a camera object positioned to face it.

<div align="center">
  <a href="Images\Image Classification Tutorial\Image 02.png" target="_blank">
    <img src="Images\Image Classification Tutorial\Image 02.png"/>
  </a>
</div>

### 3. Importing a Model
At Futurist Acoustics > EasyComputerVision > Models, you will see that this folder does not yet contain a model. The text file in this directory details where to get a model. Many models can be obtained already in the ONNX format at the [ONNX Model Zoo](https://github.com/onnx/models) You can use the ConvNeXt Nano model, which is a small and modern model trained on the ImageNet datset to classify a selection of 1,000 images. Download it from [here](https://github.com/onnx/models/blob/main/Computer_Vision/convnext_nano_Opset16_timm/convnext_nano_Opset16.onnx) and place it inside the Mode ls folder.

<div align="center">
  <a href="Images\Image Classification Tutorial\Image 03.png" target="_blank">
    <img src="Images\Image Classification Tutorial\Image 03.png"/>
  </a>
</div>

### 4. Setup
Select the EasyComputerVision game object. This object contains the EasyCVImageClassification script component. From the project window, drag the model to the ONNX field located under Setup. You will see the name of the model appear in this field.

<div align="center">
  <a href="Images\Image Classification Tutorial\Image 04.png" target="_blank">
    <img src="Images\Image Classification Tutorial\Image 04.png"/>
  </a>
</div>

As you can see, the in-game camera has already been set as the input camera. This is used as the input to our model. The Auto Create Input Texture boolean is also set to true because the camera input must be passed to a render texture before being input to the model. Auto Create Input Texture removes this intermediary step. It gets the model input dimensions to create the render texture and will automatically fill in the Input Texture field on run. You can create your own render texture if you'd like, just leave this boolean unticked and drag your render texture into the Input Texture field in order to do this.

We also allow different ways to run inference under Inference Type. We recommend using either of the Scheduled Execution inference options for less computationally intense inference. If you're using one of the On Key Press options, you can define the key in the Key drop down. By default this is the letter 'I' (for inference).

For this demo, set the Inference Type to Keypress so that when you press 'I' then inference will run.

Setting View Input to true under Helper allows you to view the input texture that is input to the model as a canvas. You can adjust the size and position of the canvas' image by adjusting the X Position, Y Position, and Scale.

### 5. Inference
Run the game and press 'I' to run inference. Assuming Show Results in Console is still set to true, you will see the prediction results in the console. An integer will appear and its confidence probability. The integer indicates the prediction, which can be checked against a full list of labels to see what the prediction is [here](https://github.com/FuturistAcoustics/EasyComputerVision/blob/main/Models/ImageNet/Labels.txt). The ConvNeXt models makes accurate predictions on the provided images which rotate between 96, 97, 98, 99, and 100.

<div align="center">
  <a href="Images\Image Classification Tutorial\Image 05.png" target="_blank">
    <img src="Images\Image Classification Tutorial\Image 05.png"/>
  </a>
</div>

### 6. Appendix
You can also use the webcam as input by setting Use Webcam to true in the Input section.

Under Engine Type, the backend can be set. By default, we use the most GPU efficient engine. More can be learnt about the options by hovering your mouse over this field or at the [Sentis docs](https://docs.unity3d.com/Packages/com.unity.sentis@1.2/manual/create-an-engine.html?q=worker).

-----

EasyComputerVision is created by [Futurist Acoustics](https://futuristacoustics.com/) <a href="https://futuristacoustics.com/"><img src="https://futuristacoustics.com/wp-content/uploads/2022/12/Media-Asset-Logo-1024%E2%80%8A%C3%97%E2%80%8A1130-928x1024.png" width=14px></a>.

[Purchase EasyComputerVision on the Unity Asset Store](https://u3d.as/37DT) <a href="https://u3d.as/37DT"><img src="https://github.com/FuturistAcoustics/EasyComputerVision/raw/main/Images/EasyComputerVision%20Logo%20192x192.png" width=14px></a>
