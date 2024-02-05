*** Archived ***

Tutorial for EasyComputerVision versions equal to and less than 1.0.2


## Intro Tutorial
This tutorial details how to use the demo project included in EasyComputerVision, which involves using an in-game camera as input to a neural network for image classification and viewing the output.

### 1. Project Setup
Create and save an empty 3D Unity project. EasyComputerVision requires the Barracuda dependency. An easy way to add Barracuda is by closing the project, navigating to your project in your file browser, then opening Packages > manifest.json. When you have manifest.json open, add 
`"com.unity.barracuda":  "3.0.0"` to the list of dependencies. You can add it to the top of the list:

![alt text](https://github.com/FuturistAcoustics/EasyComputerVision/blob/main/Images/Tutorial%201.0.2/Tutorial_01.png "Tutorial_1")

Next, open a project. In Unity go to "Window" > "Packet Manager". In the Packet Manager that opens, change "Packages:" to "Packages: My Assets". Select EasyComputerVision, then Download, then Import. The import will appear in the project window.

![alt text](https://github.com/FuturistAcoustics/EasyComputerVision/blob/main/Images/Tutorial%201.0.2/Tutorial_02.png "Tutorial_2")

### 2. Opening the Demo Scene
Open the demo scene by going to Futurist Acoustics > EasyComputerVision > Demo > ImageClassificationDemo. You will see a cube with an image of a duck on it and a camera object positioned to face it.

![alt text](https://github.com/FuturistAcoustics/EasyComputerVision/blob/main/Images/Tutorial%201.0.2/Tutorial_03.png "Tutorial_3")

### 3. Importing a Model
At Futurist Acoustics > EasyComputerVision > Models, you will see that this folder does not yet contain a model. For this demo we provide a simple ResNet50 model in the required ONNX format trained on the imagenet dataset. This model will classify images and can be downloaded from [here](https://github.com/FuturistAcoustics/EasyCV/tree/main/Models). Place this model inside the Models folder.

![alt text](https://github.com/FuturistAcoustics/EasyComputerVision/blob/main/Images/Tutorial%201.0.2/Tutorial_04.png "Tutorial_4")

### 4. Setup
Select the EasyCV game object. This object contains the ImageClassification script compponent. From the project window, drag the model to the Model Asset field located under Backend. You will see the name of the model in this field.

![alt text](https://github.com/FuturistAcoustics/EasyComputerVision/blob/main/Images/Tutorial%201.0.2/Tutorial_05.png "Tutorial_5")

As you can see, the in-game camera has already been set as the input camera. This is used as the input to our model. The Auto Create Render Texture boolean is also set to true because the camera input must be passed to a render texture before being input to the model. Auto Create Render Texture removes this intermediary step. It gets the model input dimensions to create the render texture and will automatically fill in the Input Render Texture field on run. You can create your own render texture if you'd like, just leave this field unticked and drag your render texture into the Input Render Texture field.

We also allow different ways to run inference; we recommend using either of the Scheduled Execution inference options for less computationally intense inference. If you're using one of the On Key Press options, you can define the key in the Key drop down. By default this is the letter 'I' (for inference).

Under the Debug field, Display Input as Canvas is set to true, allowing you to view the input texture that is input to the model as a canvas. You can adjust the size and position of the canvas' image by adjusting the X Position Input, Y Position Input, and Scale Factor Input.

### 5. Inference
Run the game to run inference. Assuming the inference type is set to the default of On Interval Scheduled Execution, the predictions will be continuosly populated under the Predicted section. As the image is of a Drake, the predicted value is 97. You can check the full labels [here](https://gist.github.com/yrevar/942d3a0ac09ec9e5eb3a).

![alt text](https://github.com/FuturistAcoustics/EasyComputerVision/blob/main/Images/Tutorial%201.0.2/Marketing_02.png "Tutorial_6")


### 6. Appendix
You can also use the webcam as input by setting Use Webcam to true in the Input section.

Under Engine, the Worker Type can be set. By default, we use the most GPU efficient engine. More can be learnt about them by hovering your mouse over this field or at the [Barracuda docs](https://docs.unity3d.com/Packages/com.unity.barracuda@3.0/manual/Worker.html).
