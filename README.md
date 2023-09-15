<p align="center">
  <img src="https://github.com/FuturistAcoustics/EasyComputerVision/blob/main/Images/EasyComputerVision%20Logo%20192x192.png">
</p>
<p align="center">
  <a href="https://futuristacoustics.com/"><img src="https://futuristacoustics.com/wp-content/uploads/2023/09/Futurist-Acoustics-Logo-Favicon.png" width=25px></a>
  <a href="https://www.linkedin.com/company/futurist-acoustics/"><img src="https://raw.githubusercontent.com/gauravghongde/social-icons/9d939e1c5b7ea4a24ac39c3e4631970c0aa1b920/SVG/White/LinkedIN_white.svg" width=28px></a>
  <a href="https://www.youtube.com/@futuristacoustics"><img src="https://raw.githubusercontent.com/gauravghongde/social-icons/9d939e1c5b7ea4a24ac39c3e4631970c0aa1b920/SVG/White/Youtube_white.svg" width=28px></a>
  <a href="https://www.reddit.com/r/FuturistAcoustics/"><img src="https://raw.githubusercontent.com/gauravghongde/social-icons/9d939e1c5b7ea4a24ac39c3e4631970c0aa1b920/SVG/White/Reddit_white.svg" width=28px></a>
  <a href="https://twitter.com/FutAcoustics"><img src="https://raw.githubusercontent.com/gauravghongde/social-icons/9d939e1c5b7ea4a24ac39c3e4631970c0aa1b920/SVG/White/Twitter_white.svg" width=28px></a>
  <a href="https://github.com/FuturistAcoustics"><img src="https://raw.githubusercontent.com/gauravghongde/social-icons/9d939e1c5b7ea4a24ac39c3e4631970c0aa1b920/SVG/White/Github_white.svg" width=28px></a>
</p>

# EasyComputerVision
EasyComputerVision is a Unity plugin that integrates [Barracuda](https://docs.unity3d.com/Packages/com.unity.barracuda@3.0/manual/TensorHandling.html) with a code-free interface to offer an easy way to run ML/DL computer vision models inside the Unity Game Engine. It allows you to use Barracuda code-free and currently provides an easy method for image classification (with more use-cases to come). Simply create an in-game camera or use your webcam and add an ONNX model to your project to easily run a model. EasyComputerVision is created by [Futurist Acoustics](https://futuristacoustics.com/) <a href="https://futuristacoustics.com/"><img src="https://futuristacoustics.com/wp-content/uploads/2022/12/Media-Asset-Logo-1024%E2%80%8A%C3%97%E2%80%8A1130-928x1024.png" width=14px></a>.

[Purchase EasyComputerVision on the Unity Asset Store](https://u3d.as/37DT) <a href="https://u3d.as/37DT"><img src="https://github.com/FuturistAcoustics/EasyComputerVision/raw/main/Images/EasyComputerVision%20Logo%20192x192.png" width=14px></a>

-----


## Intro Tutorial
This tutorial details how to use the demo project included in EasyComputerVision, which involves using an in-game camera as input to a neural network for image classification and viewing the output.

### 1. Project Setup
Create and save an empty 3D Unity project. EasyComputerVision requires the Barracuda dependency. An easy way to add Barracuda is by closing the project, navigating to your project in your file browser, then opening Packages > manifest.json. When you have manifest.json open, add 
`"com.unity.barracuda":  "3.0.0"` to the list of dependencies. You can add it to the top of the list:

![alt text](https://github.com/FuturistAcoustics/EasyComputerVision/blob/main/Images/Tutorial_01.png?raw=true "Tutorial_1")

Next, open a project. In Unity go to "Window" > "Packet Manager". In the Packet Manager that opens, change "Packages:" to "Packages: My Assets". Select EasyComputerVision, then Download, then Import. The import will appear in the project window.

![alt text](https://github.com/FuturistAcoustics/EasyComputerVision/blob/main/Images/Tutorial_02.png?raw=true "Tutorial_2")

### 2. Opening the Demo Scene
Open the demo scene by going to Futurist Acoustics > EasyComputerVision > Demo > ImageClassificationDemo. You will see a cube with an image of a duck on it and a camera object positioned to face it.

![alt text](https://github.com/FuturistAcoustics/EasyComputerVision/blob/main/Images/Tutorial_03.png?raw=true "Tutorial_3")

### 3. Importing a Model
At Futurist Acoustics > EasyComputerVision > Models, you will see that this folder does not yet contain a model. For this demo we provide a simple ResNet50 model in the required ONNX format trained on the imagenet dataset. This model will classify images and can be downloaded from [here](https://github.com/FuturistAcoustics/EasyCV/tree/main/Models). Place this model inside the Models folder.

![alt text](https://github.com/FuturistAcoustics/EasyComputerVision/blob/main/Images/Tutorial_04.png?raw=true "Tutorial_4")

### 4. Setup
Select the EasyCV game object. This object contains the ImageClassification script compponent. From the project window, drag the model to the Model Asset field located under Backend. You will see the name of the model in this field.

![alt text](https://github.com/FuturistAcoustics/EasyComputerVision/blob/main/Images/Tutorial_05.png?raw=true "Tutorial_5")

As you can see, the in-game camera has already been set as the input camera. This is used as the input to our model. The Auto Create Render Texture boolean is also set to true because the camera input must be passed to a render texture before being input to the model. Auto Create Render Texture removes this intermediary step. It gets the model input dimensions to create the render texture and will automatically fill in the Input Render Texture field on run. You can create your own render texture if you'd like, just leave this field unticked and drag your render texture into the Input Render Texture field.

We also allow different ways to run inference; we recommend using either of the Scheduled Execution inference options for less computationally intense inference. If you're using one of the On Key Press options, you can define the key in the Key drop down. By default this is the letter 'I' (for inference).

Under the Debug field, Display Input as Canvas is set to true, allowing you to view the input texture that is input to the model as a canvas. You can adjust the size and position of the canvas' image by adjusting the X Position Input, Y Position Input, and Scale Factor Input.

### 5. Inference
Run the game to run inference. Assuming the inference type is set to the default of On Interval Scheduled Execution, the predictions will be continuosly populated under the Predicted section. As the image is of a Drake, the predicted value is 97. You can check the full labels [here](https://gist.github.com/yrevar/942d3a0ac09ec9e5eb3a).

![alt text](https://github.com/FuturistAcoustics/EasyComputerVision/blob/main/Images/Marketing_02.png?raw=true "Tutorial_6")


### 6. Appendix
You can also use the webcam as input by setting Use Webcam to true in the Input section.

Under Engine, the Worker Type can be set. By default, we use the most GPU efficient engine. More can be learnt about them by hovering your mouse over this field or at the [Barracuda docs](https://docs.unity3d.com/Packages/com.unity.barracuda@3.0/manual/Worker.html).


-----

## Development
### Capabilities Checklist
Our aim is to see how many of the Computer Vision model types available at [Hugging Face](https://huggingface.co/models) we can implement given the constraints of Barracuda:
- [x] Image Classification
- [ ] Image Segmentation
- [ ] Depth Estimation
- [ ] Object Detection
- [ ] Image-to-Image
- [ ] Unconditional Image Generation
- [ ] Video Classification
- [ ] Zero-Shot Image Classification

#### Image Classification ✅
A range of CNNs can be used to classify images from an in-game camera or using your webcam. A majority of CNN models work, including for both greyscale and color inputs)
##### Models Tested
✅ [ViT-Base-Patch16–224](https://huggingface.co/google/vit-base-patch16-224)
✅ [GoogLeNet](https://pytorch.org/hub/pytorch_vision_googlenet/)
✅ [ResNet-50](https://huggingface.co/microsoft/resnet-50)

### Features
#### EasyComputerVision - V1.1.0
- [ ] New unticked item from Capabilities Checklist

#### EasyComputerVision - V1.0.1
- [x] Input can be normalized. The input image can be set to values between 0 and 1 or 0 and 255
- [x] Can view a summary of the model for convenience, including input and output.
- [x] Scheduled execution can be fine-tuned. The number of model layers processed per frame can be configured, enabling greated control of the inference overhead.

#### EasyComputerVision - V1.0.0
- [x] Image classification
- [x] Can use in-game camera as input
- [x] Can use webcam as input
- [x] Automatically creates a render texture using the model's input dimensions
- [x] Inference on update
- [x] Inference on interval
- [x] Inference on interval using scheduled execution
- [x] Inference on key press
- [x] Inference on key press using scheduled execution
- [x] Can use ComputePrecompiled (GPU - highly efficient GPU code with all overhead code stripped away and precompiled into the worker)
- [x] Can use Compute (GPU - highly efficient GPU but with some logic overhead)
- [x] Can use ComputeRef (GPU - a less efficient but more stable reference implementation)
- [x] Can use CSharpBurst (CPU - highly efficient, jobified and parallelized CPU code compiled via Burst)
- [x] Can use CSharp (CPU - slightly less efficient CPU code)
- [x] Can use CSharpRef (CPU - a less efficient but more stable reference implementation)
- [x] Can display input render texture as image on a canvas
- [x] Can change position and size of canvas image
