# Forest-Fire-Detection
CNN based Forest Fire Detection for camera equipped edge devices.

Recent escalation in Wildfire events have posited a need of early Fire/Smoke detection systems. While state-of-the-art approaches in this domain are concentrated on *video-based* solutions, the complexity of such algorithms is indisputably higher. A single pass, *image-based* algorithm could be easily deployed on edge devices with minimal cost and resources.

Initial focus of this project is to achieve comparable results on a proposed dataset, resolving all the known corner cases, which will then incline towards retaining the achieved performance with efficient architectures. 

Dataset is created by extracting frames from YouTube videos, querying google images and aggregating from various sources such as [dataturks](https://dataturks.com/). 

Some of the challenging test-cases I'm trying to address are:

|                        Cloud vs Smoke                        |                        Sunset vs Fire                        |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
| <img src="docs/fumes_vs_cloud.png" alt="Cloud vs Fumes256x256" style="zoom: 25%;" /> | <img src="docs/sunset_vs_fire.jpg" alt="Sunset vs Fire" style="zoom: 25%;" /> |



Initial dataset was having only **471** images in total, hence lead to better results (90+). However, after identifying the corner cases and aligning dataset with them, I've diverse, more challenging distribution as follows:


| Class    | Examples |
|----------|:----------:|
| Cloud    | 400  |
| Fire     | 755     |
| Smoke | 564    |
| Non-fire | 754    |
| Total | **2473** |

### Todos:

- [X] Baseline notebooks in Keras, fastai and **fastai2 (current experiments)**
- [X] Deployment pipeline for Raspberry Pi (using tflite)
- [ ] Implement Multilabel Classification
- [ ] Multiclass to binary mapping

### Results

| Model Name             | Error Rate | Precision | Recall | F1 Score |
| ---------------------- | :--------: | :-------: | :----: | -------- |
| xresnet50-sa-mish-r128 |   25.49    |   74.51   | 74.51  | 74.51    |
| xresnet50-sa-mish-r192 |   18.90    |   81.10   | 81.10  | 81.10    |
