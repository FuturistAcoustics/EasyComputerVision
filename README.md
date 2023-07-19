# EasyComputerVision
EasyComputerVision is a Unity plugin that uses [Barracuda](https://docs.unity3d.com/Packages/com.unity.barracuda@3.0/manual/TensorHandling.html) at the backend to offer an easy way to run ML/DL models inside the Unity Game Engine. It allows you to use Barracuda code free.

EasyComputerVision provides an easy method for image classification. Simply create an in-game camera or use your webcam and add an ONNX model to your project to easily run the model. 

## Intro Tutorial
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
#### EasyComputerVision - V1.0.0
- [x] Image classification
- [x] Can use in-game camera as input
- [ ] Can use webcam as input
- [x] Automatically creates a render texture using the model's input dimensions
- [ ] Automatically installs Barracuda
- [x] Inference on update
- [x] Inference on update using scheduled execution
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

#### EasyComputerVision - V1.0.1
- [ ] Scheduled execution adapts to number of layers in the model
