# A.	Dataset Information
In accordance with the guidelines delineated by Gebru et al. [23], the present section duly furnishes a comprehensive datasheet elucidating pertinent attributes of the ETHICS dataset.
Legal Compliance. Within the context of LeetCode, specifically in the context of its challenges labeled as "hp25" and "hp50," the process of extracting pertinent components, including the textual content of questions, verified solution approaches, and corresponding evaluation cases, is undertaken from online platforms dedicated to coding challenges. Notably, the primary source website for this data retrieval is LeetCode itself. It is crucial to highlight that the data extraction procedure is exclusively limited to publicly accessible information. This approach ensures that content from subscription-based sections of websites is not subjected to scraping activities. It is pertinent to mention that in the case of the Kattis platform, the problems subjected to data extraction fall under the purview of the Creative Commons Attribution-ShareAlike 3.0 Unported (CC BY-SA 3.0) license, as stipulated by the following link: https://creativecommons.org/licenses/by-sa/3.0/. However, it is noteworthy that for other web-based platforms, the potential for copyrighted content to be encountered remains a distinct possibility. In these cases, we abide by Fair Use §107: “the fair use of a copyrighted work, including such use by ... scholarship, or research, is not an infringement of copyright”, where fair use is determined by “the purpose and character of the use, including whether such use is of a commercial nature or is for nonprofit educational purposes”, “the amount and substantiality of the portion used in relation to the copyrighted work as a whole”, and “the effect of the use upon the potential market for or value of the copyrighted work.” The dataset derived from LeetCode's "hp25" and "hp50" challenges is explicitly designated as noncommercial in nature, and its utilization is unlikely to exert any discernible impact on the intrinsic value of the underlying original problems. It is imperative to underscore that our data acquisition process selectively targets a subset of the entire gamut of problems and their corresponding verified solutions from diverse sources.

# B.	Motivation
For what purpose was the dataset created? The LeetCode hp25 and hp50 dataset was created to track the progress of code assessment models on the task of evaluating arbitrary Python code from complex natural language specifications.
Who created the dataset (e.g., which team, research group) and on behalf of which entity (e.g., company, institution, organization)? Refer to the main document.
Who funded the creation of the dataset? If there is an associated grant, please provide the name of the grantor and the grant name and number. There is no associated grant.
Any other comments? A sample of crawled data is shown in Table 4.

```
Table 4. Sample of Crawled Data

class Solution(object):
    def twoSum(self, nums, target):
        dict = {}
        for i in range(len(nums)):
            if nums[i] in dict:
                return [dict[nums[i]], i]
            else:
                dict[target - nums[i]] = i
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        a, res, start = dict(), 0, -1
        for i, ch in enumerate(s):
            if ch in a:
                start = max(start, a[ch])
            res, a[ch] = max(res, i-start), i
        return res
```

# C.	Composition
What do the instances that comprise the dataset represent (e.g., documents, photos, people, countries)? Are there multiple types of instances (e.g., movies, users, and ratings; people and interactions between them; nodes and edges)? Please provide a description. 
The instances are coding challenge problems and posed solutions, each of which consists of question text, user posted solutions, and test cases. Please refer to the main document for more detail.
How many instances are there in total (of each type, if appropriate)? hp25 and hp50 dataset contains 100 problem questions, 200 test cases and 71,592 solutions.
Does the dataset contain all possible instances or is it a sample (not necessarily random) of instances from a larger set? If the dataset is a sample, then what is the larger set? Is the sample representative of the larger set (e.g., geographic coverage)? If so, please describe how this representativeness was validated/verified. If it is not representative of the larger set, please describe why not (e.g., to cover a more diverse range of instances, because instances were withheld or unavailable). 
LeetCode hp25 and hp50 dataset contains a subset of all possible solutions for its problems. 
What data does each instance consist of? “Raw” data (e.g., unprocessed text or images) or features? In either case, please provide a description. Each instance consists of text and numerical data.
Is there a label or target associated with each instance? If so, please provide a description. Each instance is associated with test cases, which provide a ground-truth signal for functional correctness.
Is any information missing from individual instances? If so, please provide a description, explaining why this information is missing (e.g., because it was unavailable). This does not include intentionally removed information, but might include, e.g., redacted text. Yes. There is some missing data. The reason is that some of the solutions have fewer solutions posted. A histogram of the crawled dataset can be viewed in Figure 13. ![Histogram of Questions](https://github.com/tisage/codeQuality/blob/411efaba8b735cc5fb6ecf96b221351a56b18f3c/figure/Figure%2013%20Histogram%20of%20Questions.png)

Are relationships between individual instances made explicit (e.g., users’ movie ratings, social network links)? If so, please describe how these relationships are made explicit. No.
Are there recommended data splits (e.g., training, development/validation, testing)? If so, please provide a description of these splits, explaining the rationale behind them. We provide training, validation, and test split. Refer to the main document.
Are there any errors, sources of noise, or redundancies in the dataset? If so, please provide a description. See Section 3.D Correctness Score in the main paper.
Is the dataset self-contained, or does it link to or otherwise rely on external resources (e.g., websites, tweets, other datasets)? The dataset is self-contained.
Does the dataset contain data that, if viewed directly, might be offensive, insulting, threatening, or might otherwise cause anxiety? If so, please describe why. No.
Does the dataset relate to people? If not, you may skip the remaining questions in this section. Yes.
Does the dataset identify any subpopulations (e.g., by age, gender)? If so, please describe how these subpopulations are identified and provide a description of their respective distributions within the dataset. No.
Is it possible to identify individuals (i.e., one or more natural persons), either directly or indirectly (i.e., in combination with other data) from the dataset? If so, please describe how. No.
Does the dataset contain data that might be considered sensitive in any way (e.g., data that reveals racial or ethnic origins, sexual orientations, religious beliefs, political opinions or union memberships, or locations; financial or health data; biometric or genetic data; forms of government identification, such as social security numbers; criminal history)? If so, please provide a description. No.
Any other comments? No

# D.	Collection Process
How was the data associated with each instance acquired? Was the data directly observable (e.g., raw text, movie ratings), reported by subjects (e.g., survey responses), or indirectly inferred/derived from other data (e.g., part-of-speech tags, model-based guesses for age or language)? If data was reported by subjects or indirectly inferred/derived from other data, was the data validated/verified? If so, please describe how. All data was collected by scraping problems from coding challenge websites, LeetCode.
What mechanisms or procedures were used to collect the data (e.g., hardware apparatus or sensor, manual human curation, software program, software API)? How were these mechanisms or procedures validated? We used off-the-shelf and custom-built scrapers. We conducted a manual verification to ensure that the scraped data corresponded accurately with the text present on the websites.
If the dataset is a sample from a larger set, what was the sampling strategy (e.g., deterministic, probabilistic with specific sampling probabilities)? Some problems we scraped were left out of dataset for various reasons, e.g., they required input from keyboard to continue and does not follow the testing cases format to solve, they lacked ground-truth solutions and test cases, or they were duplicate problems.
Who was involved in the data collection process (e.g., students, crowdworkers, contractors) and how were they compensated (e.g., how much were crowdworkers paid)? All data was collected by the authors of this paper.
Over what timeframe was the data collected? Does this timeframe match the creation timeframe of the data associated with the instances (e.g., recent crawl of old news articles)? If not, please describe the timeframe in which the data associated with the instances was created.
Data was collected from early 2023 to mid-2023 and refined for six months.
Were any ethical review processes conducted (e.g., by an institutional review board)? If so, please provide a description of these review processes, including the outcomes, as well as a link or other access point to any supporting documentation No.
Does the dataset relate to people? If not, you may skip the remainder of the questions in this section. Yes.
Did you collect the data from the individuals in question directly, or obtain it via third parties or other sources (e.g., websites)? We collected data by extracting information from websites where individuals had openly shared solutions to various problems.
Were the individuals in question notified about the data collection? If so, please describe (or show with screenshots or other information) how notice was provided, and provide a link or other access point to, or otherwise reproduce, the exact language of the notification itself.
Given that the examples were publicly posted by users on the internet, there was no notification sent to them regarding our data collection activities.
Did the individuals in question consent to the collection and use of their data? If so, please describe (or show with screenshots or other information) how consent was requested and provided, and provide a link or other access point to, or otherwise reproduce, the exact language to which the individuals consented. N/A
If consent was obtained, were the consenting individuals provided with a mechanism to revoke their consent in the future or for certain uses? If so, please provide a description, as well as a link or other access point to the mechanism (if appropriate). N/A
Has an analysis of the potential impact of the dataset and its use on data subjects (e.g., a data protection impact analysis) been conducted? If so, please provide a description of this analysis, including the outcomes, as well as a link or other access point to any supporting documentation. No.
Any other comments? No. 

# E.	Preprocessing/Cleaning/Labeling
Was any preprocessing/cleaning/labeling of the data done (e.g., discretization or bucketing, tokenization, part-of-speech tagging, SIFT feature extraction, removal of instances, processing of missing values)? If so, please provide a description. If not, you may skip the remainder of the questions in this section. Yes, as described in Section 3.B of the main paper.
Was the “raw” data saved in addition to the preprocessed/cleaned/labeled data (e.g., to support unanticipated future uses)? If so, please provide a link or other access point to the “raw” data. No.
Is the software used to preprocess/clean/label the instances available? If so, please provide a link or other access point. Not at this time.
Any other comments? No. 

# F.	Uses
Has the dataset been used for any tasks already? If so, please provide a description. Yes, see the main paper.
Is there a repository that links to any or all papers or systems that use the dataset? If so, please provide a link or other access point. No.
What (other) tasks could the dataset be used for? N/A
Is there anything about the composition of the dataset or the way it was collected and preprocessed/cleaned/labeled that might impact future uses? For example, is there anything that a future user might need to know to avoid uses that could result in unfair treatment of individuals or groups (e.g., stereotyping, quality of service issues) or other undesirable harms (e.g., financial harms, legal risks) If so, please provide a description. Is there anything a future user could do to mitigate these undesirable harms? In Appendix A, we outline the legal compliance of our data collection process.
Are there tasks for which the dataset should not be used? If so, please provide a description. N/A
Any other comments? No

# G.	Distribution
Will the dataset be distributed to third parties outside of the entity (e.g., company, institution, organization) on behalf of which the dataset was created? If so, please provide a description. Yes, the dataset will be publicly distributed.
How will the dataset be distributed (e.g., tarball on website, API, GitHub)? Does the dataset have a digital object identifier (DOI)? We will post it on GitHub.
When will the dataset be distributed? The dataset will be available in late 2023.
Will the dataset be distributed under a copyright or other intellectual property (IP) license, and/or under applicable terms of use (ToU)? If so, please describe this license and/or ToU, and provide a link or other access point to, or otherwise reproduce, any relevant licensing terms or ToU, as well as any fees associated with these restrictions. The code for our experimental framework is distributed under an MIT license. 
Have any third parties-imposed IP-based or other restrictions on the data associated with the instances? If so, please describe these restrictions, and provide a link or other access point to, or otherwise reproduce, any relevant licensing terms, as well as any fees associated with these restrictions. n situations where the websites from which we extract data have copyright policies, we adhere to the principles of Fair Use as defined in §107. Additionally, we uphold compliance with GDPR standards, even though all the sources of problems with verified solutions are situated within the US. Further information can be found in Appendix A.
Do any export controls or other regulatory restrictions apply to the dataset or to individual instances? If so, please describe these restrictions, and provide a link or other access point to, or otherwise reproduce, any supporting documentation. No.
Any other comments? No

# H.	Maintenance
Who is supporting/hosting/maintaining the dataset? Refer to the main document. How can the owner/curator/manager of the dataset be contacted (e.g., email address)? Refer to the main document.
Is there an erratum? If so, please provide a link or other access point. Not at this time.
Will the dataset be updated (e.g., to correct labeling errors, add new instances, delete instances)? If so, please describe how often, by whom, and how updates will be communicated to users (e.g., mailing list, GitHub)? We plan to update the dataset with coding top 500 with test cases present in the question text for each problem. This will be available through GitHub.
If the dataset relates to people, are there applicable limits on the retention of the data associated with the instances (e.g., were individuals in question told that their data would be retained for a fixed period of time and then deleted)? If so, please describe these limits and explain how they will be enforced. No.
Will older versions of the dataset continue to be supported/hosted/maintained? If so, please describe how. If not, please describe how its obsolescence will be communicated to users. N/A
If others want to extend/augment/build on/contribute to the dataset, is there a mechanism for them to do so? If so, please provide a description. Will these contributions be validated/verified? If so, please describe how. If not, why not? Is there a process for communicating/distributing these contributions to other users? If so, please provide a description. Our dataset could be extended with additional problems following the format.
Any other comments? No





