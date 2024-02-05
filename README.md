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
EasyComputerVision is a Unity plugin that integrates the brand new [Sentis](https://docs.unity3d.com/Packages/com.unity.sentis@1.2/manual/index.html) with a code-free interface to offer an easy way to run ML/DL computer vision models inside the Unity Game Engine. It allows you to use Sentis code-free and currently provides an easy method for image classification (with more use-cases to come). Simply create an in-game camera or use your webcam and add an ONNX model to your project to easily run a model. EasyComputerVision is created by [Futurist Acoustics](https://futuristacoustics.com/) <a href="https://futuristacoustics.com/"><img src="https://futuristacoustics.com/wp-content/uploads/2022/12/Media-Asset-Logo-1024%E2%80%8A%C3%97%E2%80%8A1130-928x1024.png" width=14px></a>.

[Purchase EasyComputerVision on the Unity Asset Store](https://u3d.as/37DT) <a href="https://u3d.as/37DT"><img src="https://github.com/FuturistAcoustics/EasyComputerVision/raw/main/Images/EasyComputerVision%20Logo%20192x192.png" width=14px></a>

-----
## Tutorials
- [Image Classification Tutorial](https://github.com/FuturistAcoustics/EasyComputerVision/blob/main/Tutorials/Image%20Classification%20Tutorial.md)
- [Object Detection Tutorial](https://github.com/FuturistAcoustics/EasyComputerVision/blob/main/Tutorials/Object%20Detection%20Tutorial.md)

-----
## Development
### Capabilities Checklist
Our aim is to see how many of the Computer Vision model types available at [Hugging Face](https://huggingface.co/models) we can implement given the constraints of Sentis:
- [x] Image Classification
- [x] Object Detection
- [ ] Image Segmentation
- [ ] Depth Estimation
- [ ] Image-to-Image
- [ ] Unconditional Image Generation
- [ ] Video Classification
- [ ] Zero-Shot Image Classification

#### Image Classification ✅
A range of CNNs can be used to classify images from an in-game camera or using your webcam. A majority of CNN models work, including for both greyscale and color inputs. The ONNX model zoo has recently been updated with numerous ONNX models.
##### Models Tested
✅ [ViT-Base-Patch16–224](https://huggingface.co/google/vit-base-patch16-224)
✅ [GoogLeNet](https://pytorch.org/hub/pytorch_vision_googlenet/)
✅ [ResNet-50](https://huggingface.co/microsoft/resnet-50)
✅ [ConvNeXt Nano](https://github.com/onnx/models/blob/main/Computer_Vision/convnext_nano_Opset16_timm/convnext_nano_Opset16.onnx)
✅ [ConvNeXt Tiny](https://github.com/onnx/models/blob/main/Computer_Vision/convnext_tiny_Opset16_timm/convnext_tiny_Opset16.onnx)
✅ [ConvNeXt Large](https://github.com/onnx/models/tree/main/Computer_Vision/convnext_large_Opset16_timm)

#### Object Detection ✅
##### Models Tested
✅ [YOLOv7 Tiny](https://huggingface.co/unity/sentis-yolotinyv7/blob/main/yolov7-tiny.onnx)

### Features
#### EasyComputerVision - V1.2.0
- [x] Object detection using YOLO Tiny v7

#### EasyComputerVision - V1.1.0 (refactoring for Sentis and more)
- [x] Uses the new Unity Sentis, replacing Unity Barracuda
- [x] Show results in console
- [x] Apply softmax to the output to view the probabilities as a percentage

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

-----

EasyComputerVision is created by [Futurist Acoustics](https://futuristacoustics.com/) <a href="https://futuristacoustics.com/"><img src="https://futuristacoustics.com/wp-content/uploads/2022/12/Media-Asset-Logo-1024%E2%80%8A%C3%97%E2%80%8A1130-928x1024.png" width=14px></a>.

[Purchase EasyComputerVision on the Unity Asset Store](https://u3d.as/37DT) <a href="https://u3d.as/37DT"><img src="https://github.com/FuturistAcoustics/EasyComputerVision/raw/main/Images/EasyComputerVision%20Logo%20192x192.png" width=14px></a>
