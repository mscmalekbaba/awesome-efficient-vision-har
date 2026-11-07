<!--lint disable awesome-github-->
# Awesome Efficient Vision HAR [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

_Last updated: 2026-11-07._

A curated list of resources for resource-efficient vision-based Human Activity Recognition (HAR), with a strong focus on industrial assembly, worker activity understanding, and real-time edge deployment.

This repository is centered on the practical challenge of recognizing human actions from video under resource constraints: low latency, lightweight models, compressed architectures, real-time inference, and action recognition in industrial settings.

Legend: `[📄 paper]` `[💻 code]` `[📦 dataset]` `[⚡ efficient]` `[📱 on-device]` `[🧪 benchmark]` `[🧠 distillation]` `[🧩 attention]` `[🔧 quantization]` `[🪓 pruning]` `[🧰 tooling]` `[📚 list]`

## Contents

1. [Industrial assembly and worker activity datasets](#industrial-assembly-and-worker-activity-datasets)
2. [Efficient video backbones and action-recognition models](#efficient-video-backbones-and-action-recognition-models)
3. [Pruning, compression, and distillation](#pruning-compression-and-distillation)
4. [Real-time and edge deployment](#real-time-and-edge-deployment)
5. [General video HAR datasets and benchmarks](#general-video-har-datasets-and-benchmarks)
6. [Surveys and evaluation protocols](#surveys-and-evaluation-protocols)
7. [Useful tools and libraries](#useful-tools-and-libraries)
8. [Contribution guidelines](#contribution-guidelines)

## Industrial assembly and worker activity datasets

- [NTU RGB+D](https://rose1.ntu.edu.sg/dataset/actionRecognition/) (2016) — Large RGB+D human activity dataset, useful for motion-centric and skeleton-based manufacturing workflows. `[📦 dataset]`
- [PKU-MMD](https://www.icst.pku.edu.cn/struct/Projects/PKUMMD.html) (2017) — Large-scale multimodal dataset for long-duration human activity recognition. `[📦 dataset]`
- [EPIC-KITCHENS](https://epic-kitchens.github.io/) (2018) — Egocentric activity and object interaction dataset relevant to hands-on worker behavior and operational workflows. `[📦 dataset]`
- [Toyota Smarthome](https://project.inria.fr/toyotasmarthome/) (2019) — Realistic daily living and action recognition dataset with long temporal sequences and multi-camera views. `[📦 dataset]`
- [Assembly101](https://assembly-101.github.io/) (2021) — Large-scale multi-view dataset for procedural activities, assembly workflows, and worker-centric action understanding. `[📦 dataset]`
- [IKEA ASM](https://github.com/ikea/ikea-asm) (2021) — Furniture assembly sequence dataset useful for procedural and fine-grained action analysis. `[📦 dataset]`
- [MMAct](https://github.com/olivesgatech/MMAct) — Multimodal action dataset combining RGB/video, inertial, and wearable signals for human activity understanding. `[📦 dataset]`

## Efficient video backbones and action-recognition models

- [TSN (Temporal Segment Networks)](https://github.com/yjxiong/temporal-segment-networks) (2016) — Efficient video classification by sparse temporal sampling; a strong lightweight baseline. `[📄 paper] [💻 code] [⚡ efficient]`
- [ShuffleNet V2](https://github.com/megvii-research/ShuffleNet-Series) (2018) — Efficient mobile architecture emphasizing real hardware throughput. `[📄 paper] [⚡ efficient] [📱 on-device]`
- [R(2+1)D](https://github.com/irwon/gru) (2018) — Factorized spatiotemporal convolutions that reduce cost compared with full 3D CNNs. `[📄 paper] [⚡ efficient]`
- [MobileNetV3](https://github.com/tensorflow/models/tree/master/research/slim) (2019) — Widely used lightweight backbone for resource-constrained vision pipelines. `[📄 paper] [⚡ efficient]`
- [EfficientNet](https://github.com/tensorflow/tpu/tree/master/models/official/efficientnet) (2019) — Compound scaling strategy for compact high-performing CNNs. `[📄 paper] [⚡ efficient]`
- [TSM (Temporal Shift Module)](https://github.com/mit-han-lab/temporal-shift-module) (2019) — Lightweight temporal modeling with strong accuracy/latency trade-offs. `[📄 paper] [💻 code] [⚡ efficient]`
- [SlowFast](https://github.com/facebookresearch/SlowFast) (2019) — Dual-path architecture for efficient action recognition with strong motion modeling. `[📄 paper] [💻 code] [⚡ efficient]`
- [X3D](https://github.com/facebookresearch/SlowFast/tree/main/projects/x3d) (2020) — Efficient 3D CNN family with good accuracy–latency scaling. `[📄 paper] [💻 code] [⚡ efficient]`
- [MoViNet](https://github.com/google-research/movinet) (2021) — Mobile video network designed for efficient, low-latency recognition. `[📄 paper] [💻 code] [⚡ efficient] [📱 on-device]`
- [MobileViT](https://github.com/apple/ml-cvnets) (2021) — Hybrid CNN-transformer backbone for mobile-friendly visual recognition. `[📄 paper] [💻 code] [⚡ efficient] [📱 on-device]`
- [VideoMAE](https://github.com/MCG-NJU/VideoMAE) (2022) — Masked autoencoding framework for video representation learning and transfer to action recognition. `[📄 paper] [💻 code] [🧠 distillation]`
- [MViT](https://github.com/facebookresearch/SlowFast/tree/main/projects/mvit) (2022) — Multiscale transformer for video recognition with strong performance/efficiency balance. `[📄 paper] [💻 code] [⚡ efficient]`
- [TinyVideoNet](https://github.com/mit-han-lab/tinyvideonet) (2023) — Compact video backbone designed for edge deployment. `[📄 paper] [💻 code] [⚡ efficient]`

## Pruning, compression, and distillation

- [FitNets](https://arxiv.org/abs/1412.6550) (2014) — Hint-based distillation using intermediate feature maps. `[📄 paper] [🧠 distillation]`
- [Distilling the Knowledge in a Neural Network](https://arxiv.org/abs/1503.02531) (2015) — Foundational teacher-student distillation objective. `[📄 paper] [🧠 distillation]`
- [Deep Compression](https://arxiv.org/abs/1510.00149) (2015) — Classical prune-quantize-Huffman pipeline for compact models. `[📄 paper] [🪓 pruning] [🔧 quantization]`
- [The Lottery Ticket Hypothesis](https://arxiv.org/abs/1803.03635) (2018) — Sparse subnetworks can match dense models after training. `[📄 paper] [🪓 pruning]`
- [TinyBERT](https://arxiv.org/abs/1909.10351) (2019) — Distillation for compact transformer inference. `[📄 paper] [🧠 distillation]`
- [DistilBERT](https://arxiv.org/abs/1910.01108) (2019) — Practical distillation recipe with strong runtime gains. `[📄 paper] [🧠 distillation]`
- [PyTorch Quantization](https://pytorch.org/docs/stable/quantization.html) (2019) — Built-in quantization for production-oriented deployment. `[🧰 tooling] [🔧 quantization]`
- [Movement Pruning](https://arxiv.org/abs/2005.07683) (2020) — Structured pruning strategy for sparse, deployable models. `[📄 paper] [🪓 pruning]`
- [MobileBERT](https://arxiv.org/abs/2004.02984) (2020) — Distilled transformer optimized for mobile deployment. `[📄 paper] [🧠 distillation]`
- [AIMET (AI Model Efficiency Toolkit)](https://github.com/quic/aimet) (2021) — Model compression toolkit with quantization and pruning support. `[💻 code] [🧰 tooling] [🔧 quantization] [🪓 pruning]`

## Real-time and edge deployment

- [TensorFlow Lite](https://www.tensorflow.org/lite) — Standard mobile and edge deployment stack for compact inference. `[🧰 tooling] [📱 on-device]`
- [ONNX Runtime](https://onnxruntime.ai/) — Cross-platform runtime with optimization support for edge devices. `[🧰 tooling] [📱 on-device]`
- [Apache TVM](https://tvm.apache.org/) — Compiler stack for accelerator-aware model optimization. `[🧰 tooling] [📱 on-device]`
- [LiteRT for Microcontrollers](https://ai.google.dev/edge/litert/microcontrollers/overview) — TinyML deployment path for microcontroller-class devices. `[🧰 tooling] [📱 on-device]`
- [CMSIS-NN](https://github.com/ARM-software/CMSIS-NN) — Optimized kernels for Arm Cortex-M devices. `[💻 code] [📱 on-device]`
- [MLPerf Tiny](https://github.com/mlcommons/tiny) — Collection of tiny/edge AI benchmarks for deployment evaluation. `[🧪 benchmark] [📱 on-device]`
- [Perfetto](https://perfetto.dev/) — System tracing for latency, scheduling, and runtime overhead. `[🧰 tooling] [🧪 benchmark]`
- [PyTorch ExecuTorch](https://pytorch.org/executorch/stable/) (2023) — On-device inference runtime for resource-constrained deployment. `[🧰 tooling] [📱 on-device]`

## General video HAR datasets and benchmarks

- [HMDB51](https://serre-lab.clps.brown.edu/resource/hmdb-a-large-human-motion-database/) (2011) — Common benchmark for short-form human action recognition. `[📦 dataset] [🧪 benchmark]`
- [UCF101](https://www.crcv.ucf.edu/data/UCF101.php) (2012) — Classic action dataset with 101 classes and extensive benchmarking usage. `[📦 dataset] [🧪 benchmark]`
- [Charades](https://prior.allenai.org/projects/charades) (2016) — Long-range everyday activity recognition in realistic settings. `[📦 dataset]`
- [Kinetics-400](https://deepmind.google/opensource/kinetics/) (2017) — Large-scale benchmark for video understanding and action classification. `[📦 dataset] [🧪 benchmark]`
- [Something-Something V2](https://developer.qualcomm.com/software/ai-datasets/something-something) (2017) — Motion-heavy benchmark focused on temporal reasoning. `[📦 dataset] [🧪 benchmark]`
- [Kinetics-700](https://deepmind.google/opensource/kinetics/) (2019) — Expanded benchmark for more diverse action recognition tasks. `[📦 dataset] [🧪 benchmark]`
- [AVA](https://research.google.com/ava/) — Spatiotemporal atomic action dataset for action detection tasks. `[📦 dataset]`

## Surveys and evaluation protocols

- [TinyML Benchmarking and Deployment Challenges](https://arxiv.org/abs/2003.04821) (2020) — Relevant for resource-aware deployment and repeated benchmarking. `[📄 paper] [🧪 benchmark]`
- [A Survey of Human Activity Recognition in Video](https://arxiv.org/) — Broad overview of visual HAR methods and design choices. `[📄 paper]`
- [Deep Learning for Human Activity Recognition in Videos](https://arxiv.org/) — Review spanning CNN, RNN, and transformer video recognition pipelines. `[📄 paper]`
- [Video Understanding: A Survey](https://arxiv.org/) — Greater context for video understanding, action recognition, and temporal modeling. `[📄 paper]`
- [Efficient Vision Transformers for Video Recognition](https://arxiv.org/) — Useful background for lightweight transformer designs. `[📄 paper]`

A strong evaluation protocol for industrial HAR should report:

- model parameters and memory footprint
- MACs/FLOPs for a fixed input window
- throughput and end-to-end latency on target hardware
- power and energy proxy measurements when possible
- accuracy on subject-wise splits and realistic deployment conditions
- robustness to occlusion, viewpoint changes, and motion blur

## Useful tools and libraries

- [Awesome Efficient HAR](https://github.com/sumeyye-agac/awesome-efficient-har) — Complementary wearable and IMU-centric HAR resource list. `[📚 list]`
- [PaddleVideo](https://github.com/PaddlePaddle/PaddleVideo) — Video understanding toolkit and action-recognition model zoo. `[💻 code]`
- [MMAction2](https://github.com/open-mmlab/mmaction2) — Action recognition toolbox with many video models and training pipelines. `[💻 code]`
- [PyTorch Video](https://github.com/facebookresearch/pytorchvideo) — PyTorch-based video learning library for action recognition research. `[💻 code]`
- [TorchVision](https://github.com/pytorch/vision) — Useful for image/video pipelines and pretrained visual backbones. `[💻 code]`

## Contribution guidelines

Please keep entries focused on:

- resource-efficient visual HAR
- industrial and assembly-related worker activity recognition
- edge or real-time deployment
- lightweight backbones and model compression
- pruning, quantization, or distillation
- benchmarking and repeatable evaluation

Suggested entry format:

- Title
- Year
- One-sentence description
- Links to paper, code, and dataset if relevant
- Tags such as `[📄 paper]`, `[💻 code]`, `[📦 dataset]`, `[⚡ efficient]`, `[📱 on-device]`, `[🧠 distillation]`, `[🪓 pruning]`, `[🔧 quantization]`

## License

This repository is provided for research and educational use. If a specific paper or dataset has its own license, respect that license.
