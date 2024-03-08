# NetEaseCrowd

NetEaseCrowd: A Dataset for Long-term and Online Crowdsourcing Truth Inference

## Introduction

We introduce NetEaseCrowd, a large-scale crowdsourcing annotation dataset based on 
a mature Chinese data crowdsourcing platform of NetEase Inc.. 
NetEaseCrowd dataset contains about **2,400** workers, **1,000,000** tasks, and **6,000,000** annotations between them, 
where the annotations are collected in about 6 months. 
In this dataset, we provide ground truths for all the tasks and record timestamps for all the annotations.


### Task example
A task example in NetEaseCrowd:

<img src="assets/task_example.png" width="500"/>

Each task contains one true label.

### Comparison with existing datasets

Compared with the existing crowdsourcing datasets, our NetEaseCrowd dataset has the following characteristics:

| Characteristic | Existing datasets                                    | NetEaseCrowd dataset                                      |
| -------------- | ---------------------------------------------------- | --------------------------------------------------------- |
| Scability      | Relatively small sizes in #workers/tasks/annotations | Lage-scale data collection with 6 millions of annotations |
| Timestamps     | Short-term data with no timestamps recorded          | Complete timestamps recorded during a 6-month timespan    |
| Task Type      | Single type of tasks                                 | Various task types with different required cabilities     |



<!-- ## Citation

If you use the dataset in your work, please cite:

    @inproceedings{TODO} -->

## Dataset Statistics

The basic statistics of NetEaseCrowd dataset and other previous datasets are as follows:
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

The NetEaseCrowd dataset is provided in partitions under the `data/` folder of this repository in the csv file format. Each partition is named as `NetEaseCrowd_part_x.csv`. Concat them to get the entire NetEaseCrowd dataset.

### Dataset Format

In the dataset, each line of record represents an interaction between a worker and a task, with the following columns:

*   **tasksetId**: the unique id of the task set containing the annotated task. Each task belongs to exactly one task set.
*   **taskId**: the unique id of the annotated task.
*   **workerId**: the unique id of the worker.
*   **answer**: the annotation given by the worker, which is an enumeric number starting from 0.
*   **completeTime**: the integer timestamp recording the completion time of the annotation.
*   **truth**: the groundtruth of the annotated task, which, in consistency with answer, is also an enumeric number starting from 0.
*   **capability**: the unique id of the capability required by the annotated taskset. Each taskset belongs to exactly one capability.



## Baseline models

We test several existing truth inference methods in our dataset, and detailed analysis with more experimental setups can be found in our paper.

| Method         | Accuracy | F1-score |
| -------------- | -------- | -------- |
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




## License

The NetEaseCrowd dataset is licensed under [CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.en).
