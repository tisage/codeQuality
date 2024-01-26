# Code Qualiy Evaluation Dataset
Welcome to the repository for our research paper: T. Wang and Z. Chen, "Analyzing Code Text Strings for Code Evaluation," 2023 IEEE International Conference on Big Data (BigData), Sorrento, Italy, 2023, pp. 5619-5628, doi: 10.1109/BigData59044.2023.10386406.

## Contents
This repository contains the following:
- Clean Data (compressed with a password)
- Fine-tuned Model
- Data Compliance
- Appendix Figure
- License

## Data Info

| pid | title     | code                                        | score         | label_hp50 | label_hp25 | label_sp25 |
|-----|-----------|---------------------------------------------|---------------|------------|------------|------------|
| 1   | Two Sum   | ```class Solution:\n def twoSum(...)...``` | 0.594891977   | 1          | 3          | 0          |

The dataset comprises 72,079 rows of human-submitted code solutions using Python 3 for Leet Code challenges (#1 - #100), with the following key attributes:
- `pid`: LeetCode Question Number
- `title`: Question Title
- `code`: Code Solution (`string` dtype)
- `score`: Score evaluated by our Quality Engine
- `label_hp50`: Annotated label using 0.5 as the threshold (1: high quality, 0: low quality)
- `label_hp25`: Annotated label using 0.75 and 0.25 as thresholds (1: high quality, 0: low quality, 3: medium quality)
- `label_sp25`: Annotated label using group mean as the threshold (1: high quality, 0: low quality)

## Dataset Usage
*Note*: The password to access the uncompressed data can be obtained by sending a request email to twang4@mercy.edu. For any inquiries or further assistance, please feel free to contact us. Thank you for your interest in our research.

## Fine-tuned Model
See details:
[https://huggingface.co/tisage/CodeQualityLC100](https://huggingface.co/tisage/CodeQualityLC100)

## Reference
If you found the dataset useful in your research or applications, please cite using the following BibTeX:
```
@INPROCEEDINGS{10386406,
  author={Wang, Tianyu and Chen, Zhixiong},
  booktitle={2023 IEEE International Conference on Big Data (BigData)}, 
  title={Analyzing Code Text Strings for Code Evaluation}, 
  year={2023},
  volume={},
  number={},
  pages={5619-5628},
  keywords={Measurement;Deep learning;Codes;Bidirectional control;Organizations;Transformers;Software;code assessment;code annotation;deep learning;nature language processing;software assurance;code security},
  doi={10.1109/BigData59044.2023.10386406}
}
```
