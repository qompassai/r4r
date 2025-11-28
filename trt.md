* Increasing SMM Efficiency

TLDR: Using consumer-grade hardware to improve small Open Neural Network Exchange (ONNX) video inference models:

**BiRefNet-general-bb_swin_v1_tiny-epoch_232**

```bash
#  BiRefNet is capable of handling background removal tasks for images and videos via efficient inference on-devices. It uses advanced neural network architectures like Swin Transformer.

trtexec --onnx=BiRefNet-general-bb_swin_v1_tiny-epoch_232.onnx --saveEngine=BiRefNet-general.trt --fp16 --memPoolSize=workspace:4096 --verbose --useCudaGraph --useSpinWait --noDataTransfers --builderOptimizationLevel=5 --tilingOptimizationLevel=3 --profilingVerbosity=detailed --exportTimes=timing.json --exportProfile=profile.json --exportLayerInfo=layers.json --separateProfileRun --avgRuns=100 --persistentCacheRatio=1.0 --maxAuxStreams=4 --warmUp=500 --duration=60 --iterations=100 --device=0}
```

**Isnet-anime**

```bash
#Isnet-anime is optimized specifically to detect and remove backgrounds in scenarios involving anime or secondary characters. This makes it ideal for artistic or creative projects where the input data involves stylized or animated visuals.

trtexec --onnx=isnet-anime.onnx --saveEngine=BiRefNet-general.trt --fp16 --memPoolSize=workspace:4096 --verbose --useCudaGraph --useSpinWait --builderOptimizationLevel=5 --tilingOptimizationLevel=3 --profilingVerbosity=detailed --exportTimes=timing.json --exportProfile=profile.json --exportLayerInfo=layers.json --separateProfileRun --avgRuns=100 --persistentCacheRatio=1.0 --maxAuxStreams=4 --warmUp=500 --duration=60 --iterations=100 --device=0 --exposeDMA  --timeDeserialize --timeRefit}
```

```
Where:
- --onnx} represents the input ONNX model path
- --saveEngine} specifies the output TensorRT engine path
- --fp16} enables half-precision floating point optimization
- --memPoolSize} allocates workspace memory in MiB
- --builderOptimizationLevel} sets optimization level (1-5)
- --tilingOptimizationLevel} configures tiling optimization (0-4)
- --avgRuns} defines the number of inference runs for averaging
- --warmUp} specifies warm-up iterations before timing
- --duration} sets profiling duration in seconds
- --iterations} defines the number of inference iterations
- --maxAuxStreams} configures concurrent CUDA streams
- --persistentCacheRatio} sets cache persistence (0-1)
- --exposeDMA enables the exposure of Direct Memory Access (DMA) for performance.
- --timeDeserialize enables timing measurement for engine deserialization.
- --timeRefit enables timing for the engine refitting process.
```
**Run with TensorRT 10.8, CUDA 12.8, nvidia-open-dkms on Arch Linux-Zen 6.13-4-1 x86_64**
