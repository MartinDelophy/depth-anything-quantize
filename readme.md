[![ONNX](https://img.shields.io/badge/ONNX-grey)](https://onnx.ai/)

# Depth Anything ONNX for browser
quantize model for web to use Depth Anything

<img src="./sample.png" alt="Latency Comparison" width=45%>
<img src="./result.png" alt="Latency Comparison" width=45%>

## onnx quantize export 
the original model i have download from depth anything onnx release page, then i convert from that.
you can see the model in models directory and see the demo in index.html

``` python
import onnx
from onnxruntime.quantization import quantize_dynamic, QuantType

model_fp32 = './depth_anything_vits14.onnx'
model_quant = './depth_anything_vits14.quant.onnx'
quantized_model = quantize_dynamic(model_fp32, model_quant, weight_type=QuantType.QUInt8)

```


## Credits
If you use any ideas from the papers or code in this repo, please consider citing the authors of [Depth Anything](https://arxiv.org/abs/2401.10891) and [DINOv2](https://arxiv.org/abs/2304.07193) and [Depth Anything Onnx](https://github.com/fabio-sim/Depth-Anything-ONNX). Lastly, if the ONNX versions helped you in any way, please also consider starring this repository.

```bibtex
@article{depthanything,
      title={Depth Anything: Unleashing the Power of Large-Scale Unlabeled Data}, 
      author={Yang, Lihe and Kang, Bingyi and Huang, Zilong and Xu, Xiaogang and Feng, Jiashi and Zhao, Hengshuang},
      journal={arXiv:2401.10891},
      year={2024}
}
```

```bibtex
@misc{oquab2023dinov2,
  title={DINOv2: Learning Robust Visual Features without Supervision},
  author={Oquab, Maxime and Darcet, Timothée and Moutakanni, Theo and Vo, Huy V. and Szafraniec, Marc and Khalidov, Vasil and Fernandez, Pierre and Haziza, Daniel and Massa, Francisco and El-Nouby, Alaaeldin and Howes, Russell and Huang, Po-Yao and Xu, Hu and Sharma, Vasu and Li, Shang-Wen and Galuba, Wojciech and Rabbat, Mike and Assran, Mido and Ballas, Nicolas and Synnaeve, Gabriel and Misra, Ishan and Jegou, Herve and Mairal, Julien and Labatut, Patrick and Joulin, Armand and Bojanowski, Piotr},
  journal={arXiv:2304.07193},
  year={2023}
}
```
