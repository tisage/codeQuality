Welcome to the repository for our research paper titled "Analyzing Code Text Strings for Code Evaluation."

## Contents
This repository contains the following:

- License
- Data Compliance
- Appendix Figure
- Clan Data (compressed with a password)
- Fine-tuned Model (will be uploaded soon)
## Data Info

| pid | title     | code                                        | score         | label_hp50 | label_hp25 | label_sp25 |
|-----|-----------|---------------------------------------------|---------------|------------|------------|------------|
| 1   | Two Sum   | ```class Solution:
                        def twoSum(self, nums: List[int], target: int) -> List[int]:
                            for i in range(len(nums)):
                                for j in range(i + 1, len(nums)):
                                    if nums[j] == target - nums[i]:
                                        return [i, j]```                             | 0.594891977   | 1          | 3          | 0          |




The dataset comprises 72,079 rows of human-submitted solutions for LeetCode challenges, with the following key attributes:

`pid`: LeetCode Question Number
`title`: Question Title
`code`: Python 3 Code Solution
`score`: Score evaluated by our Quality Engine
`label_hp50`: Annotated label using 0.5 as the threshold (1: high quality, 0: low quality)
`label_hp25`: Annotated label using 0.75 and 0.25 as thresholds (1: high quality, 0: low quality, 3: medium quality)
`label_sp25`: Annotated label using group mean as the threshold (1: high quality, 0: low quality)

## Dataset Usage
If you plan to use the dataset provided in this repository, we kindly request that you cite our paper:

*T. Wang, Z. Chen, Analyzing Code Text Strings for Code Evaluation, in: Proceeding 2023 IEEE International Conference on Big Data (BigData), (Sorrento, Italy, 2023), pp. 5619.*

Note: The password to access the uncompressed data can be obtained by sending a request email to twang4@mercy.edu

For any inquiries or further assistance, please feel free to contact us. Thank you for your interest in our research.


since 2023
T. Wang
