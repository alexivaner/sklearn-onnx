# GMM sklearn-onnx Modified Library to Support Baraccuda Unity
### This is forked version of sklearn-onnx as my requirement to use ONNX in Baraccuda Unity, Please if you want to use this library refer to its original version since maybe my modification still contain a lot of bugs!
Credit to [xiadupre](https://github.com/xadupre) and [phrabat](https://github.com/prabhat00155) (Contributors for original library) that helps me a lot to use ONNX in Unity and help me a lot when I requested new features to added and gave me some instruction how to modify this library. I also want to say my credit to [AlexRibard](https://github.com/AlexRibard) from Baraccuda-Unity that give me some clue about how we could use baraccuda supported ONNX operator, so I still could use unsupported ONNX operator using supported one.

## Link to original documentation about library and baraccuda unity
[sklearn-onnx](https://github.com/onnx/sklearn-onnx)<br>
[baraccuda-for-unity](https://docs.unity3d.com/Packages/com.unity.barracuda@0.3/manual/index.html)<br>
[baraccuda-github](https://github.com/Unity-Technologies/barracuda-release)<br>


## What I modified and Why to do so?
I just changed the gaussian-mixture part from this library to support Baraccuda-Unity since Baraccuda still could support just limited operation in ONNX but of course they will add new features soon.<br>
### What are changed 
ReduceLogSumExpx to -> y = exp(x) -> z = reduce_sum(y) -> log(z) for ReduceLogSumExp<br>
and<br>
ReduceSumSquarex to -> y = x^2 -> z = reduce_sum(y)<br>
This is because ReduceLogSumExp and ReduceSumSquare still not supported by baraccuda.

### Here is my discussion with them
[Baraccuda-Unity-Issue](https://github.com/Unity-Technologies/barracuda-release/issues/37)<br>
[sklearn-onnx-issue](https://github.com/onnx/sklearn-onnx/issues/451)<br>

<p align="center"><img width="50%" src="docs/logo_main.png" /></p>

| Linux | Windows |
|-------|---------|
| [![Build Status](https://dev.azure.com/onnxmltools/sklearn-onnx/_apis/build/status/sklearn-onnx-linux-conda-ci?branchName=master)](https://dev.azure.com/onnxmltools/sklearn-onnx/_build/latest?definitionId=5?branchName=master) | [![Build Status](https://dev.azure.com/onnxmltools/sklearn-onnx/_apis/build/status/sklearn-onnx-win32-conda-ci?branchName=master)](https://dev.azure.com/onnxmltools/sklearn-onnx/_build/latest?definitionId=5?branchName=master)|

## Introduction 
*sklearn-onnx* converts [scikit-learn](https://scikit-learn.org/stable/) models to [ONNX](https://github.com/onnx/onnx). Once in the ONNX format, you can use tools like [ONNX Runtime](https://github.com/Microsoft/onnxruntime) for high performance scoring.

## Documentation
Full documentation including tutorials is available at [http://onnx.ai/sklearn-onnx/](http://onnx.ai/sklearn-onnx/).

You may also find answers in [existing issues](https://github.com/onnx/sklearn-onnx/issues?utf8=%E2%9C%93&q=is%3Aissue)
or submit a new one.

## Installation
You can install from [PyPi](https://pypi.org/project/skl2onnx/):
```
pip install skl2onnx
```
Or you can install from the source with the latest changes.
```
pip install git+https://github.com/onnx/sklearn-onnx.git
```

If you install *sklearn-onnx* from its source code, you must set the environment variable `ONNX_ML=1` before installing the onnx package.

## Contribute
We welcome contributions in the form of feedback, ideas, or code. 

## License
[MIT License](LICENSE)
