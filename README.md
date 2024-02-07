# NetEaseCrowd

NetEaseCrowd: A Dataset for Long-term and Online Crowdsourcing Truth Inference

## Introduction

We introduce NetEaseCrowd, a large-scale crowdsourcing annotation dataset based on a mature Chinese data crowdsourcing platform of NetEase Inc.. NetEaseCrowd dataset contains about 2,400 workers, 1,000,000 tasks, and 6,000,000 annotations between them, where the annotations are collected in about 6 months. In this dataset, we provide groundtruths for all the tasks and record timestamps for all the annotations.

Compared with the existing crowdsourcing datasets, our NetEaseCrowd dataset has following characteristics:

| Characteristic | Existing datasets                                    | NetEaseCrowd dataset                                      |
| -------------- | ---------------------------------------------------- | --------------------------------------------------------- |
| Scability      | Relatively small sizes in #workers/tasks/annotations | Lage-scale data collection with 6 millions of annotations |
| Timestamps     | Short-term data with no timestamps recorded          | Complete timestamps recorded during a 6-month timespan    |
| Task Type      | Single type of tasks                                 | Various task types with different required cabilities     |

<!-- ## Citation

If you use the dataset in your work, please cite:

    @inproceedings{TODO} -->

## Dataset Statistics

The basic statistics of NetEaseCrowd dataset shows as follow:

|               | NetEaseCrowd |
| ------------- | ------------ |
| #Workers      | 2,413        |
| #Tasks        | 999,799      |
| #Groundtruths | 999,799      |
| #Annotations  | 6,016,319    |

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



<!-- 
## License

This repository is liciensed under Apache-2.0 License.

The NetEaseCrowd dataset is liciensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/). -->
