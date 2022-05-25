# ClaimDiff

This repository contains the data for our paper: *Miyoung Ko, Ingyu Seong, Hwaran Lee, Joonsuk Park, Minsuk Chang, Minjoon Seo. "[Beyond Fact Verification: Comparing and Contrasting Claims on Contentious Topics](https://arxiv.org/abs/2205.12221)*".

- Please contact Miyoung Ko `miyoung@kaist.ac.kr` and Ingyu Seong `ingyu.ee@gmail.com`, or leave Github issues for suggestions and comments.
- For more details about this dataset, see the [paper](https://arxiv.org/abs/2205.12221).

## Dataset

### Data

The ClaimDiff dataset includes 2,941 claim pairs extracted from 274 articles with 137 topics. We extract the pairs from a group of articles sharing the same topic, released by multiple presses. The diverse views on contentious topics can be obtained by collecting the claims written by different authors and presses. We present the ClaimDiff dataset as ClaimDiff-S and ClaimDiff-W, which is as follows:

```
🗃 ClaimDiff
├── 📁 ClaimDiff-S
│   ├── ClaimDiff-strength-train.json
│   ├── ClaimDiff-strength-test.json
│   └── ClaimDiff-strength-test-full.json
└── 📁 ClaimDiff-W
    ├── ClaimDiff-weak-train.json
    ├── ClaimDiff-weak-test.json
    └── ClaimDiff-weak-test-full.json
```

### Statistics
We release our main ClaimDiff dataset {`Train`, `Test`} along with an additional `Test-full` dataset. `Test-full` can be considered an unfiltered test dataset to encounter the real-world distribution over whole articles, resulting in a high ratio of unrelated pairs.


|              |  Train |  Test  | Test-full |
|:------------:|:------:|:------:|:---------:|
|     Pairs    |  1,857 |  1,084 |   3,173   |
|    Topics    |   90   |   44   |     44    |
|   Articles   |   180  |   88   |     88    |
| % Strengthen | 69.31% | 56.64% |   19.35%  |
|   % Weaken   | 10.61% | 22.05% |   7.69%   |

### Data Format

`ClaimDiff-{strength,weak}-{train,test,test-full}.json` files contains a list of dictionary that represents a single instance, with the following keys:

```json
{
	"topic": "str(Topic of the claim pair)",
	"date": "str(Published date of Article A)",
	"pair_id": "str(Unique pair ID)",
	"claim_a": "str(Claim A from Article A, c_1)",
	"claim_b": "str(Claim B from Article B, c_2)",
	"article_a": "str(Title of Article A)",
	"article_b": "str(Title of Article B)",
	"relation": "int(0 or 1)",
	"rationle": "List[str]",
}
```


## Citation


Please cite our paper in your publications if you find the ClaimDiff dataset useful:

```latex
@misc{https://doi.org/10.48550/arxiv.2205.12221,
  doi = {10.48550/ARXIV.2205.12221},  
  url = {https://arxiv.org/abs/2205.12221}, 
  author = {Ko, Miyoung and Seong, Ingyu and Lee, Hwaran and Park, Joonsuk and Chang, Minsuk and Seo, Minjoon},
  title = {Beyond Fact Verification: Comparing and Contrasting Claims on Contentious Topics}, 
  publisher = {arXiv},
  year = {2022},
}
```

