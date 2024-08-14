# Generous Teacher: Good at distilling Knowledge for Student Learning (IMAVIS 2024)

This is the official code for "Generous Teacher: Good at distilling Knowledge for Student Learning", accepted by Image and Vision Computing 2024.

Paper link: https://www.sciencedirect.com/science/article/pii/S0262885624003044

## Abstract
Knowledge distillation is a technique that aims to transfer valuable knowledge from a large, well-trained model (the teacher) to a lightweight model (the student), with the primary goal of improving the student's performance on a given task. In recent years, mainstream distillation methods have focused on modifying student learning styles, resulting in less attention being paid to the knowledge provided by the teacher. However, upon re-examining the knowledge transferred by the teacher, we find that it still has untapped potential, which is crucial to bridging the performance gap between teachers and students. Therefore, we study knowledge distillation from the teacher's perspective and introduce a novel teacher knowledge enhancement method termed “Generous Teacher.” The Generous Teacher is a specially trained teacher model that can provide more valuable knowledge for the student model. This is achieved by integrating a standardly trained teacher (Standard Teacher) to assist in the training process of the Generous Teacher. As a result, the Generous Teacher accomplishes the task at hand and assimilates distilled knowledge from the Standard Teacher, effectively adapting to distillation teaching in advance. Specifically, we recognize that non-target class knowledge plays a crucial role in improving the distillation effect for students. To leverage this, we decouple logit outputs and selectively use the Standard Teacher's non-target class knowledge to enhance the Generous Teacher. By setting the temperature as a multiple of the logit standard deviation, we ensure that the additional knowledge absorbed by the Generous Teacher is more suitable for student distillation. Experimental results on standard benchmarks demonstrate that the Generous Teacher surpasses the Standard Teacher in terms of accuracy when applied to standard knowledge distillation. Furthermore, the Generous Teacher can be seamlessly integrated into existing distillation methods, bringing general improvements at a low additional computational cost.

![Fig 1](https://github.com/EifelTing/Generous-Teacher/blob/main/Fig%201.svg)

## Environment

- python3.6+
- pytorch1.5+
- ...

## Training

```
python train.py
```

## Acknowledgements


