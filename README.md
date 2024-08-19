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
For instance, in a gesture comparison task, each task includes three choices, 
two of which feature similar gestures, while the third does not.
Annotators are required to pick out the different one. An example is shown below:

<center>
<img src="assets/task_example.png" width="500"/>
</center>

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
