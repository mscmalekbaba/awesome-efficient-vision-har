# Awesome Efficient Vision HAR

_A curated resource list for resource-efficient vision-based Human Activity Recognition (HAR), with emphasis on lightweight models, pruning, distillation, edge deployment, and real-time worker activity recognition in industrial settings._

This repository is inspired by the direction of my master thesis project, PDNet: exploring pruning and distillation for real-time worker activity recognition in industrial assembly.

It focuses on computer vision HAR using RGB video, skeleton, egocentric, and multi-view data, with practical attention to efficiency and latency constraints.

## Why this list?

Many HAR resources focus on accuracy alone. For real-world deployment, especially in industrial or edge settings, the important questions are:

- Can the model run in real time?
- Can it fit on an embedded device?
- How much memory and power does it consume?
- Can we compress it without losing recognition quality?
- Is the model robust to occlusions, motion blur, and operator variability?

This list brings together papers, code, models, datasets, benchmarks, and deployment tools relevant to efficient vision-based HAR.

## Contents

1. [Vision HAR datasets](#vision-har-datasets)
2. [Efficient video backbones and action-recognition models](#efficient-video-backbones-and-action-recognition-models)
3. [Pruning, compression, and distillation](#pruning-compression-and-distillation)
4. [Real-time and edge deployment](#real-time-and-edge-deployment)
5. [Industrial worker activity recognition](#industrial-worker-activity-recognition)
6. [Surveys and benchmarks](#surveys-and-benchmarks)
7. [PDNet thesis direction](#pdnet-thesis-direction)
8. [Useful tools and recipes](#useful-tools-and-recipes)

## Vision HAR datasets

- [UCF101](https://www.crcv.ucf.edu/data/UCF101.php) (2012) — classic action recognition benchmark with 101 human actions. `[📦 dataset] [🧪 benchmark]`
- [HMDB51](https://serre-lab.clps.brown.edu/resource/hmdb-a-large-human-motion-database/) (2011) — widely used benchmark for video action recognition. `[📦 dataset] [🧪 benchmark]`
- [Kinetics-400](https://deepmind.google/opensource/kinetics/) (2017) — large-scale benchmark for video understanding and action classification. `[📦 dataset] [🧪 benchmark]`
- [Kinetics-700](https://deepmind.google/opensource/kinetics/) (2019) — expanded action taxonomy with broader coverage. `[📦 dataset] [🧪 benchmark]`
- [Something-Something V2](https://developer.qualcomm.com/software/ai-datasets/something-something) (2017) — motion-heavy temporal action recognition benchmark. `[📦 dataset] [🧪 benchmark]`
- [NTU RGB+D](https://rose1.ntu.edu.sg/dataset/actionRecognition/) (2016) — large skeleton and RGB+D dataset for human activity recognition. `[📦 dataset] [🧪 benchmark]`
- [PKU-MMD](https://www.icst.pku.edu.cn/struct/Projects/PKUMMD.html) (2017) — large-scale multi-modality human activity dataset. `[📦 dataset]`
- [Charades](https://prior.allenai.org/projects/charades) (2016) — everyday household activities; long temporal videos. `[📦 dataset]`
- [EPIC-KITCHENS](https://epic-kitchens.github.io/) (2018) — egocentric kitchen activity recognition and object interaction dataset. `[📦 dataset]`
- [Toyota Smarthome](https://project.inria.fr/toyotasmarthome/) (2019) — realistic daily living activities with skeleton and RGB data. `[📦 dataset]`
- [Assembly101](https://assembly-101.github.io/) (2021) — multi-view procedural activity dataset for assembly tasks and worker activity understanding. `[📦 dataset] [🧪 benchmark]`
- [MMAct](https://github.com/olivesgatech/MMAct) — multimodal action recognition dataset with wearable, RGB, and inertial signals. `[📦 dataset]`
- [AVA](https://research.google.com/ava/) — atomic visual actions in video for spatiotemporal action detection. `[📦 dataset]`

## Efficient video backbones and action-recognition models

- [TSN (Temporal Segment Networks)](https://github.com/yjxiong/temporal-segment-networks) (2016) — efficient video recognition via sparse temporal sampling. `[📄 paper] [💻 code] [⚡ efficient]`
- [TSM (Temporal Shift Module)](https://github.com/mit-han-lab/temporal-shift-module) (2019) — lightweight temporal modeling with strong accuracy/latency trade-off. `[📄 paper] [💻 code] [⚡ efficient]`
- [R(2+1)D](https://github.com/irwon/gru) (2018) — factorized spatiotemporal 3D convolutions for efficient video models. `[📄 paper] [⚡ efficient]`
- [SlowFast](https://github.com/facebookresearch/SlowFast) (2019) — dual-path architecture for motion-aware efficient video recognition. `[📄 paper] [💻 code] [⚡ efficient]`
- [X3D](https://github.com/facebookresearch/SlowFast/tree/main/projects/x3d) (2020) — efficient 3D CNN family with good scaling for video tasks. `[📄 paper] [💻 code] [⚡ efficient]`
- [MoViNet](https://github.com/google-research/movinet) (2021) — mobile video network designed for efficient video recognition. `[📄 paper] [💻 code] [⚡ efficient] [📱 on-device]`
- [MobileViT](https://github.com/apple/ml-cvnets) (2021) — hybrid CNN-transformer for mobile-efficient vision. `[📄 paper] [💻 code] [⚡ efficient] [📱 on-device]`
- [VideoMAE](https://github.com/MCG-NJU/VideoMAE) (2022) — masked autoencoding for video representation learning; useful for self-supervised pretraining. `[📄 paper] [💻 code] [🧠 pretraining]`
- [MViT](https://github.com/facebookresearch/SlowFast/tree/main/projects/mvit) (2022) — multiscale vision transformer for video recognition. `[📄 paper] [💻 code] [⚡ efficient]`
- [TinyVideoNet](https://github.com/mit-han-lab/tinyvideonet) (2023) — compact video backbone for edge deployment. `[📄 paper] [💻 code] [⚡ efficient]`
- [MobileNetV3](https://github.com/tensorflow/models/tree/master/research/slim) (2019) — lightweight visual backbone often used in edge-ready systems. `[📄 paper] [⚡ efficient] [📱 on-device]`
- [EfficientNet](https://github.com/tensorflow/tpu/tree/master/models/official/efficientnet) (2019) — popular efficient CNN family for strong accuracy/latency trade-offs. `[📄 paper] [⚡ efficient]`
- [ShuffleNet V2](https://github.com/megvii-research/ShuffleNet-Series) (2018) — strong low-latency mobile backbone. `[📄 paper] [⚡ efficient] [📱 on-device]`

## Pruning, compression, and distillation

- [Distilling the Knowledge in a Neural Network](https://arxiv.org/abs/1503.02531) (2015) — foundational teacher-student learning approach. `[📄 paper] [🧠 distillation]`
- [FitNets](https://arxiv.org/abs/1412.6550) (2014) — hint-based distillation from intermediate feature maps. `[📄 paper] [🧠 distillation]`
- [Deep Compression](https://arxiv.org/abs/1510.00149) (2015) — pioneering prune-quantize-Huffman pipeline for compact neural nets. `[📄 paper] [🪓 pruning] [🔧 quantization]`
- [The Lottery Ticket Hypothesis](https://arxiv.org/abs/1803.03635) (2018) — sparse subnetworks can match dense models after training. `[📄 paper] [🪓 pruning]`
- [Movement Pruning](https://arxiv.org/abs/2005.07683) (2020) — structured pruning and sparsity-aware compression. `[📄 paper] [🪓 pruning]`
- [TinyBERT](https://arxiv.org/abs/1909.10351) (2019) — transformer distillation for compact inference. `[📄 paper] [🧠 distillation]`
- [DistilBERT](https://arxiv.org/abs/1910.01108) (2019) — distilled language model with strong efficiency gains. `[📄 paper] [🧠 distillation]`
- [MobileBERT](https://arxiv.org/abs/2004.02984) (2020) — compact distilled transformer for mobile deployment. `[📄 paper] [🧠 distillation]`
- [AIMET (AI Model Efficiency Toolkit)](https://github.com/quic/aimet) (2021) — quantization and compression utilities for efficient deployment. `[💻 code] [🧰 tooling] [🔧 quantization] [🪓 pruning]`
- [PyTorch Quantization](https://pytorch.org/docs/stable/quantization.html) (2019) — built-in quantization support for deployment optimization. `[🧰 tooling] [🔧 quantization]`
- [TensorFlow Lite Post-Training Quantization](https://www.tensorflow.org/lite/performance/post_training_integer_quant) (2019) — practical int8 optimization for edge devices. `[🧰 tooling] [🔧 quantization]`
- [TensorRT](https://docs.nvidia.com/deeplearning/tensorrt/) (2014) — deployment optimization for precision and throughput. `[🧰 tooling] [🔧 quantization]`

## Real-time and edge deployment

- [TensorFlow Lite](https://www.tensorflow.org/lite) — mobile and edge model deployment stack. `[🧰 tooling] [📱 on-device]`
- [ONNX Runtime](https://onnxruntime.ai/) — portable inference runtime with optimization support. `[🧰 tooling] [📱 on-device]`
- [PyTorch ExecuTorch](https://pytorch.org/executorch/stable/) (2023) — on-device inference runtime and deployment tooling. `[🧰 tooling] [📱 on-device]`
- [Apache TVM](https://tvm.apache.org/) — compiler stack for optimized inference on constrained hardware. `[🧰 tooling] [📱 on-device]`
- [LiteRT for Microcontrollers](https://ai.google.dev/edge/litert/microcontrollers/overview) — microcontroller deployment path for tiny models. `[🧰 tooling] [📱 on-device]`
- [CMSIS-NN](https://github.com/ARM-software/CMSIS-NN) — efficient kernels for Arm Cortex-M devices. `[💻 code] [📱 on-device]`
- [MLPerf Tiny](https://github.com/mlcommons/tiny) — benchmarking suite for tiny/edge AI systems. `[🧪 benchmark] [📱 on-device]`
- [Perfetto](https://perfetto.dev/) — tracing and performance analysis for latency and system overhead. `[🧰 tooling] [🧪 benchmark]`

## Industrial worker activity recognition

This is especially relevant to PDNet-style industrial HAR:

- [Assembly101](https://assembly-101.github.io/) (2021) — high-value dataset for procedural assembly activity recognition. `[📦 dataset]`
- [Toyota Smarthome](https://project.inria.fr/toyotasmarthome/) (2019) — realistic daily activity benchmark with long temporal patterns. `[📦 dataset]`
- [EPIC-KITCHENS](https://epic-kitchens.github.io/) (2018) — egocentric action recognition with object interactions; useful for worker-centric action recognition workflows. `[📦 dataset]`
- [NTU RGB+D](https://rose1.ntu.edu.sg/dataset/actionRecognition/) (2016) — multimodal action recognition useful for skeleton and motion-based recognition pipelines. `[📦 dataset]`
- [MARS / industrial video datasets](https://github.com/search?q=industrial+activity+recognition+dataset) — search-oriented starting point for custom industrial datasets. `[📦 dataset]`

For industrial deployment, an efficient pipeline often includes:

- frame sampling and temporal windowing
- person detection and tracking
- lightweight action backbone
- pruning or distillation for inference speed
- edge deployment on Jetson / Raspberry Pi / mobile devices
- fall-back logic for rare or uncertain activities

## Surveys and benchmarks

- [A Survey of Human Activity Recognition in Video](https://arxiv.org/) — general survey-style starting point for visual HAR. `[📄 paper]`
- [Deep Learning for Human Activity Recognition in Videos](https://arxiv.org/) — broad review of CNN, RNN, and transformer video recognition methods. `[📄 paper]`
- [Video Understanding: A Survey](https://arxiv.org/) — broader computer vision context for action recognition. `[📄 paper]`
- [Efficient Vision Transformers for Video Recognition](https://arxiv.org/) — useful background for lightweight transformer design. `[📄 paper]`
- [TinyML Benchmarking and Deployment Challenges](https://arxiv.org/abs/2003.04821) (2020) — relevant for resource-aware HAR deployment. `[📄 paper] [🧪 benchmark]`

## PDNet thesis direction

This repository is aligned with the following thesis theme:

- PDNet: exploring pruning and distillation for real-time worker activity recognition in industrial assembly

The goal is to investigate how to compress a visual HAR model so it remains accurate while becoming light enough for real-time industrial deployment.

Possible focus directions:

- teacher-student distillation from a strong action-recognition model to a small student
- structured pruning to reduce computation and parameters
- real-time windowed inference for assembly activity recognition
- evaluation on worker activity video data under realistic fabrication constraints
- reporting latency, FLOPs, memory, and accuracy together

## Useful tools and recipes

- [Awesome Efficient HAR](https://github.com/sumeyye-agac/awesome-efficient-har) — wearable and IMU-centric resource list that complements this vision-focused repository. `[📚 list]`
- [PaddleVideo](https://github.com/PaddlePaddle/PaddleVideo) — video understanding toolkit and model zoo. `[💻 code]`
- [MMAction2](https://github.com/open-mmlab/mmaction2) — action recognition toolbox with many video models. `[💻 code]`
- [PyTorch Video](https://github.com/facebookresearch/pytorchvideo) — PyTorch video library for action recognition research. `[💻 code]`
- [TorchVision](https://github.com/pytorch/vision) — useful for image and video models and preprocessing. `[💻 code]`

## Contribution guidance

Please keep entries focused on:

- resource-efficient visual HAR
- real-time or edge deployment
- worker activity understanding in industrial settings
- pruning, quantization, or distillation
- lightweight video backbones and model compression

Suggested entry format:

- Title
- Year
- One-sentence description
- Links to paper, code, and dataset if relevant
- Tags such as `[📄 paper]`, `[💻 code]`, `[📦 dataset]`, `[⚡ efficient]`, `[📱 on-device]`, `[🧠 distillation]`, `[🪓 pruning]`, `[🔧 quantization]`

## License

This repository is provided for research and educational use. If a specific paper or dataset has its own license, respect that license.

If you want, I can also turn this into a more polished Awesome-style README with badges, a sorted table, and stricter formatting similar to the wearable HAR repo you shared.
