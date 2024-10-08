# Generous teacher: Good at distilling knowledge for student learning (IMAVIS 2024)

This is the official code for "Generous teacher: Good at distilling knowledge for student learning", accepted by Image and Vision Computing 2024.

Paper link: [Click Here](https://doi.org/10.1016/j.imavis.2024.105199)

![Fig 1](https://github.com/EifelTing/Generous-Teacher/blob/main/Fig%201.svg)

## Abstract
Knowledge distillation is a technique that aims to transfer valuable knowledge from a large, well-trained model (the teacher) to a lightweight model (the student), with the primary goal of improving the student's performance on a given task. In recent years, mainstream distillation methods have focused on modifying student learning styles, resulting in less attention being paid to the knowledge provided by the teacher. However, upon re-examining the knowledge transferred by the teacher, we find that it still has untapped potential, which is crucial to bridging the performance gap between teachers and students. Therefore, we study knowledge distillation from the teacher's perspective and introduce a novel teacher knowledge enhancement method termed “Generous Teacher.” The Generous Teacher is a specially trained teacher model that can provide more valuable knowledge for the student model. This is achieved by integrating a standardly trained teacher (Standard Teacher) to assist in the training process of the Generous Teacher. As a result, the Generous Teacher accomplishes the task at hand and assimilates distilled knowledge from the Standard Teacher, effectively adapting to distillation teaching in advance. Specifically, we recognize that non-target class knowledge plays a crucial role in improving the distillation effect for students. To leverage this, we decouple logit outputs and selectively use the Standard Teacher's non-target class knowledge to enhance the Generous Teacher. By setting the temperature as a multiple of the logit standard deviation, we ensure that the additional knowledge absorbed by the Generous Teacher is more suitable for student distillation. Experimental results on standard benchmarks demonstrate that the Generous Teacher surpasses the Standard Teacher in terms of accuracy when applied to standard knowledge distillation. Furthermore, the Generous Teacher can be seamlessly integrated into existing distillation methods, bringing general improvements at a low additional computational cost.

## Environment

- torch==1.12.1
- numpy==1.17.2
- tqdm==4.36.1
- scipy==1.3.1
- ...

## Training
### Training of the standard teacher
```
python train_normal.py --save_path experiments/CIFAR10/baseline/resnet18 
```
### Training of the generous teacher
```
python train_generous.py --save_path experiments/CIFAR10/kd_generous_resnet18/generous_resnet18 --Tn 1.0 --alpha 1.0
```
### Training of the student
```
python train_kd.py --save_path experiments/CIFAR10/kd_generous_resnet18/cnn
```

## Citation
~~~
@article{
ding2024generous,
title={Generous teacher: Good at distilling knowledge for student learning},
author={Ding, Yifeng and Yang, Gaoming and Yin, Shuting and Zhang, Ji and Fang, Xianjin and Yang, Wencheng},
journal={Image and Vision Computing},
pages={105199},
year={2024},
publisher={Elsevier}
}
~~~

## Acknowledgement
* [Teacher-free KD](https://github.com/yuanli2333/Teacher-free-Knowledge-Distillation)
* [DAFL](https://github.com/huawei-noah/Data-Efficient-Model-Compression/tree/master/DAFL) 
* [DeepInversion](https://github.com/NVlabs/DeepInversion)


