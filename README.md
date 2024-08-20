# NetEaseCrowd

NetEaseCrowd: A Dataset for Long-term and Online Crowdsourcing Truth Inference

## Introduction

We introduce NetEaseCrowd, a large-scale crowdsourcing annotation dataset based on 
a mature Chinese data crowdsourcing platform of NetEase Inc.. 
NetEaseCrowd dataset contains about **2,400** workers, **1,000,000** tasks, and **6,000,000** annotations between them, 
where the annotations are collected in about 6 months. 
In this dataset, we provide ground truths for all the tasks and record timestamps for all the annotations.


### Task
The NetEaseCrowd dataset is constructed based on various types of tasks.
In detail, there are 6 different types of tasks in the dataset
(associated with different `capability` as illustrated in our paper).
There are some examples of the tasks in the dataset:

- **50: Expression similarity filtering**
    > Question: Select the image from A, B, and C that looks the least similar in expression to the other two images.
    
    <details>
    <summary>Click to show question related images</summary>
  
    ![A](./assets/samples/50_01.jpg) | ![B](/assets/samples/50_02.jpg) | ![C](/assets/samples/50_03.jpg)
  
    </details>
    
      
- **52: Naturalness of Expression Judgment**

    > Question: Select the most natural expression from the three images below
    
    <details>
    <summary>Click to show question related images</summary>
  
    ![A](./assets/samples/52_01.jpg) | ![B](/assets/samples/52_02.jpg) | ![C](/assets/samples/52_03.jpg)
    </details>


- **53: Facial Similarity Screening**

    > Question: Select the face that looks more like the reference face(first face).
    
    <details>
    <summary>Click to show question related images</summary>
  
    <div style="display: flex;">
      <img src="/assets/samples/53_01.jpeg" style="width: 25%;" />
      <img src="/assets/samples/53_02.jpeg" style="width: 25%;" /> 
      <img src="/assets/samples/53_03.jpeg" style="width: 25%;" />
    </div>
    </details>

- **56: Gesture Similarity Filter**

    > Question: Select the gesture that looks the least similar to the other two gestures.
    
    <details>
    <summary>Click to show question related images</summary>
  
    <div style="display: flex;">
      <img src="/assets/samples/56_01.png" style="width: 25%;" />
      <img src="/assets/samples/56_02.png" style="width: 25%;" /> 
      <img src="/assets/samples/56_03.png" style="width: 25%;" />
    </div>
    </details>

- **69: Article continuation classification**

    > Question: Please select the best continuation between A and B based on: 1. Information richness; 2. Sentence fluency; 3. Coherence with the previous text; 4. Logical consistency, or select 'undecided'.

     <details>
     <summary>Click to show question related content(raw content in Chinese)</summary>
  
     ```
     背景: 随着他的靠近，无形间带动一股越发猛烈的气流，他的脚步未曾停下半分，压强震裂了水泥浇灌的地面，半块凹陷成蛛网状，年轻男人紧咬牙关，迎着割裂盔甲的气流一步一步，左手展开挡在前面，右手握成拳聚起全身力气向前，数据条停了片刻，尖锐声波铺天盖地，刺眼的光突然炸开，黑洞般吞噬他的身体。
     画面顷刻定格，小心眯起眼睛，有个声音散在一片白茫茫之中，空洞的、零落的，意外有些耳熟。
     “他叫开心。”
    
     选项A: 这是小心第几次梦见开心了？他不记得了，可每当他想要回忆起什么时，就觉得脑袋像是被人用锤子狠狠砸了一下，疼得他整个人都发麻，随后便是无尽的黑暗。
    
     选项B: 小心不知道自己是怎么回到家的，那段记忆太过陌生，以至于他对此毫无印象，只是当他推开门的时候，看到屋内的景象，脑袋里轰然炸开一朵巨大的烟花。
    
     选项C：不确定
     ```
     </details>

### Comparison with existing datasets

Compared with the existing crowdsourcing datasets, our NetEaseCrowd dataset has the following characteristics:

| Characteristic | Existing datasets                                    | NetEaseCrowd dataset                                      |
|----------------|------------------------------------------------------|-----------------------------------------------------------|
| Scalability    | Relatively small sizes in #workers/tasks/annotations | Lage-scale data collection with 6 millions of annotations |
| Timestamps     | Short-term data with no timestamps recorded          | Complete timestamps recorded during a 6-month timespan    |
| Task Type      | Single type of tasks                                 | Various task types with different required capabilities   |



<!-- ## Citation

If you use the dataset in your work, please cite:

    @inproceedings{TODO} -->

## Dataset Statistics

The basic statistics of NetEaseCrowd dataset and [other previous datasets](#other-public-datasets) are as follows:
| Dataset                                    | \#Worker | \#Task  | \#Groundtruth | \#Anno    | Avg(\#Anno/worker) | Avg(\#Anno/task) | Timestamp    | Task type |
|--------------------------------------------|----------|---------|---------------|-----------|--------------------|------------------|--------------|-----------|
| NetEaseCrowd                               | 2,413    | 999,799 | 999,799       | 6,016,319 | 2,493.3            | 6.0              | ✔︎   | Multiple  |
| Adult                | 825      | 11,040  | 333           | 92,721    | 112.4              | 8.4              | ✘ | Single    |
| Birds             | 39       | 108     | 108           | 4,212     | 108.0              | 39.0             | ✘ | Single    |
| Dog                    | 109      | 807     | 807           | 8,070     | 74.0               | 10.0             | ✘ | Single    |
| CF                  | 461      | 300     | 300           | 1,720     | 3.7                | 5.7              | ✘ | Single    |
| CF\_amt             | 110      | 300     | 300           | 6030      | 54.8               | 20.1             | ✘ | Single    |
| Emotion                | 38       | 700     | 565           | 7,000     | 184.2              | 10.0             | ✘ | Single    |
| Smile             | 64       | 2,134   | 159           | 30,319    | 473.7              | 14.2             | ✘ | Single    |
| Face                | 27       | 584     | 584           | 5,242     | 194.1              | 9.0              | ✘ | Single    |
| Fact                   | 57       | 42,624  | 576           | 216,725   | 3802.2             | 5.1              | ✘ | Single    |
| MS             | 44       | 700     | 700           | 2,945     | 66.9               | 4.2              | ✘ | Single    |
| product              | 176      | 8,315   | 8,315         | 24,945    | 141.7              | 3.0              | ✘ | Single    |
| RTE                    | 164      | 800     | 800           | 8,000     | 48.8               | 10.0             | ✘ | Single    |
| Sentiment        | 1,960    | 98,980  | 1,000         | 569,375   | 290.5              | 5.8              | ✘ | Single    |
| SP                  | 203      | 4,999   | 4,999         | 27,746    | 136.7              | 5.6              | ✘ | Single    |
| SP\_amt             | 143      | 500     | 500           | 10,000    | 69.9               | 20.0             | ✘ | Single    |
| Trec               | 762      | 19,033  | 2,275         | 88,385    | 116.0              | 4.6              | ✘ | Single    |
| Tweet                 | 85       | 1,000   | 1,000         | 20,000    | 235.3              | 20.0             | ✘ | Single    |
| Web                 | 177      | 2,665   | 2,653         | 15,567    | 87.9               | 5.8              | ✘ | Single    |
| ZenCrowd\_us   | 74       | 2,040   | 2,040         | 12,190    | 164.7              | 6.0              | ✘ | Single    |
| ZenCrowd\_in   | 25       | 2,040   | 2,040         | 11,205    | 448.2              | 5.5              | ✘ | Single    |
| ZenCrowd\_all  | 78       | 2,040   | 2,040         | 21,855    | 280.2              | 10.7             | ✘ | Single    |



<!-- The basic statistics of NetEaseCrowd dataset shows as follows:

|               | NetEaseCrowd |
| ------------- | ------------ |
| #Workers      | 2,413        |
| #Tasks        | 999,799      |
| #Groundtruths | 999,799      |
| #Annotations  | 6,016,319    | -->

## Data Content and Format

### Obtain the data

Two ways to access the dataset:
* Directly download overall NetEaseCrowd in [Hugging Face](https://huggingface.co/datasets/liuhyuu/NetEaseCrowd) [**Recommended**]

* Under the [`data/` folder](https://github.com/fuxiAIlab/NetEaseCrowd-Dataset/tree/main/data), the NetEaseCrowd dataset is provided in partitions in the csv file format. Each partition is named as `NetEaseCrowd_part_x.csv`. Concat them to get the entire NetEaseCrowd dataset.

### Dataset format

In the dataset, each line of record represents an interaction between a worker and a task, with the following columns:

*   **taskId**: The unique id of the annotated task.
*   **tasksetId**: The unique id of the task set. Each task set contains unspecified number of tasks. Each task belongs to exactly one task set.
*   **workerId**: The unique id of the worker.
*   **answer**: The annotation given by the worker, which is an enumeric number starting from 0.
*   **completeTime**: The integer timestamp recording the completion time of the annotation.
*   **truth**: The groundtruth of the annotated task, which, in consistency with answer, is also an enumeric number starting from 0.
*   **capability**: The unique id of the capability required by the annotated taskset. Each taskset belongs to exactly one capability.

*For the privacy concerns, all sensitive content like as -Ids, has been anonymized.*

### Data sample

| tasksetId | taskId              | workerId | answer | completeTime  | truth | capability |
|-----------|---------------------|----------|--------|---------------|-------|------------|
| 6980      | 1012658482844795232 | 64       | 2      | 1661917345953 | 1     | 69         |
| 6980      | 1012658482844795232 | 150      | 1      | 1661871234755 | 1     | 69         |
| 6980      | 1012658482844795232 | 263      | 0      | 1661855450281 | 1     | 69         |

In the example above, there are three annotations, all from the same taskset 6980 and the same task 1012658482844795232. Three annotators, with ids 64, 150, and 263, provide annotations of 2, 1, and 0, respectively. They do the task at different time. The truth label for this task is 1, and the capability id of the task is 69.

## Baseline Models

We test several existing truth inference methods in our dataset, and detailed analysis with more experimental setups can be found in our paper.

| Method         | Accuracy | F1-score |
|----------------|----------|----------|
| MV             | 0.92695  | 0.92692  |
| DS             | 0.95178  | 0.94817  |
| MACE           | 0.95991  | 0.94957  |
| Wawa           | 0.94814  | 0.94445  |
| ZeroBasedSkill | 0.94898  | 0.94585  |
| GLAD           | 0.95064  | 0.95058  |
| EBCC           | 0.91071  | 0.90996  |
| ZC             | 0.95305  | 0.95301  |
| TiReMGE        | 0.92713  | 0.92706  |
| LAA            | 0.94173  | 0.94169  |
| BiLA           | 0.88036  | 0.87896  |

### Test with the dataset directly from crowd-kit

The NetEaseCrowd dataset has been integrated into the [crowd-kit](https://github.com/Toloka/crowd-kit)
(with pull request [here](https://github.com/Toloka/crowd-kit/pull/101)),
you can use it directly in your code with the following code(with crowd-kit version > 1.2.1):

```python
from crowdkit.aggregation import DawidSkene
from crowdkit.datasets import load_dataset

df, gt = load_dataset('netease_crowd')

ds = DawidSkene(10)
result = ds.fit_predict(df)

print(len(result))
# 999799

```

## Other public datasets
We provide a curated list for other public datasets towards truth inference task. 

| Dataset Name                                                                     | Resource                                                                                                                                                                                                                                                                                                                          |
|----------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------| 
| adult                                                                            | Quality management on amazon mechanical turk. [[paper](https://dl.acm.org/doi/abs/10.1145/1837885.1837906)][[data](https://github.com/ipeirotis/Get-Another-Label/tree/master/data)]                                                                                                                                              |
| sentiment<br>fact                                                                | Workshops Held at the First AAAI Conference on Human Computation and Crowdsourcing: A Report. [[paper](https://ojs.aaai.org/index.php/aimagazine/article/view/2537/2427)][[data](https://sites.google.com/site/crowdscale2013/home)]                                                                                              |
| MS<br>zencrowd_all<br>zencrowd_us<br>zencrowd_in<br>sp<br>sp_amt<br>cf<br>cf_amt | The active crowd toolkit: An open-source tool for benchmarking active learning algorithms for crowdsourcing research. [[paper](https://ojs.aaai.org/index.php/HCOMP/article/download/13256/13104)][[data](https://github.com/orchidproject/active-crowd-toolkit)]                                                                 |
| Product<br>tweet<br>dog<br>face<br>duck<br>relevance<br>smile                    | Truth inference in crowdsourcing: Is the problem solved? [[paper](https://hub.hku.hk/bitstream/10722/243527/1/content.pdf?accept=1)][[data](https://zhydhkcws.github.io/crowd_truth_inference/)] <br> *Note that tweet dataset is called sentiment in this source. It is different from the sentiment dataset in CrowdScale2013.* |
| bird<br>rte<br>web<br>trec                                                       | Spectral methods meet em: A provably optimal algorithm for crowdsourcing. [[paper](https://proceedings.neurips.cc/paper/2014/file/788d986905533aba051261497ecffcbb-Paper.pdf)][[data](https://github.com/zhangyuc/SpectralMethodsMeetEM)]                                                                                         |
## Citation

If you use this project in your research or work, please cite it using the following BibTeX entry:

```bibtex
@misc{wang2024dataset,
      title={A Dataset for the Validation of Truth Inference Algorithms Suitable for Online Deployment}, 
      author={Fei Wang and Haoyu Liu and Haoyang Bi and Xiangzhuang Shen and Renyu Zhu and Runze Wu and Minmin Lin and Tangjie Lv and Changjie Fan and Qi Liu and Zhenya Huang and Enhong Chen},
      year={2024},
      eprint={2403.08826},
      archivePrefix={arXiv},
      primaryClass={cs.HC}
}
```

## License

The NetEaseCrowd dataset is licensed under [CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.en).
