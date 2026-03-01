# UNBench

- Picked from the instructor-provided list

UNBench is a comprehensive multi-stage benchmark built on United Nations Security Council (UNSC) records to evaluate large language models across drafting, voting, and statement generation in high-stakes political decision-making.

## Paper

**Benchmarking LLMs for Political Science: A United Nations Perspective**  
*Yueqing Liang, Liangwei Yang, Chen Wang, Congying Xia, Rui Meng, Xiongxiao Xu, Haoran Wang, Ali Payani, Kai Shu*  
**AAAI 2026 (Oral)**  
🔗 https://arxiv.org/abs/2502.14122

## Contribution
### Reproduction (Section 1-5 in notebook)

Reproduced *Task 2（Simulate country voting behavior on draft resolutions）* by using **Llama 3.1 8B model in Together API** (one selected by the original author) to produce my own measured outputs.

Task Breakdown:
- **Goal:** Simulate voting outcomes by different countries on draft resolutions.
- **Input:** Draft resolutions and country profiles.
- **Output:** Voting results (`Y` for Yes, `N` for No, `A` for Abstain) and evaluation metrics.
- **File:** `data/task2.csv` and `data/task2/`

### Modifications across two distinct dimensions (Section 6 and 7 in notebook)

#### About prompt
Added extra information in the prompt, including:
1. Dates of draft
2. Authors(Proposing Countries) of draft
3. The above two

#### About model
Different models were employed, including:
1. Llama 4 Maverick Instruct (17Bx128E) in Together API
2. Gemini 2.0 flash in Vertex API
3. Gemini 2.5 flash lite in Vertex API

## Project Structure

```
UNBench/
│
├── data/                         # task datasets you need to download by Google Drive link
│   ├── task2.csv                 # Task 2 - Voting simulation
│   └── task2/                    # Raw draft files for Task 2
│
├── run_task2.ipynb               # Colab notebook for running experiments
│
└── README.md                     # Project description and usage guide
```

## Start Guide

The entire project runs in Colab.

1. **Keep the same project folder in Google Drive:**

   Download the notebook here and dataset by https://drive.google.com/drive/folders/1Yq0HuN2zR-MIa6lJhpuTAp9jzp3UMQzb?usp=drive_link then upload them to Google Drive. Ensure the project structure remains consistent with me.

2. **Define the absolute path to your project's root directory.**

   Change *BASE_DIR* in the notebook:

   ```python
   BASE_DIR = '/content/drive/MyDrive/FTEC5660/Individual project'
   ```
   
3. Replace the API key with your own.
   - Vertex API and Together API were used in this notebook.

   Get to [Together](https://api.together.ai/settings/api-keys) and [Vertex](https://console.cloud.google.com/vertex-ai/studio/settings/api-keys) to get your API.

   To run the notebook, your API key must be stored it in a Colab Secret named 'VERTEX_API_KEY' and 'TOGETHER_API_KEY'


4. Run the `run_task2.ipynb` file.

Further details regarding the code are provided in the text cells of the notebook.









