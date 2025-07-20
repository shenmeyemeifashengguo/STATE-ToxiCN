# STATE ToxiCN: A Benchmark for Span-level Target-Aware Toxicity Extraction in Chinese Hate Speech Detection

## 🎉 Our paper has been accepted by ACL 2025 Findings!

## Dataset
- **Training Set**: `data/train.json`
- **Test Set**: `data/test.json`

## API Integration
- API calling code is located in `api.ipynb`.
- The code is identical across instances, with only the API key changed.

## Inference and Fine-Tuning
- Inference and fine-tuning follow the LLaMA-Factory tutorial.
- Reference: [LLaMA-Factory GitHub](https://github.com/hiyouga/LLaMA-Factory/blob/main/README_zh.md)
- To avoid overfitting, we monitored the trends of training and test losses and confirmed through preliminary experiments that the performance stabilized after 10 epochs. Therefore, all models were trained for 10 epochs. We adopted the LoRA method and directly evaluated the results on the test set. To reduce hyperparameter sensitivity, we trained models for each learning rate and selected the result with the highest accuracy on the test set, then calculated the final performance by weighted averaging. The specific hyperparameters used are as follows:
  | Hyperparameters     | Value            |
  |---------------------|------------------|
  | Epochs              | 10               |
  | Batch size          | 2                |
  | Learning rate       | 1e-5, 2e-5, 3e-5, 4e-5, 5e-5 |
  | Cutoff length       | 1024             |
  | Compute type        | fp16             |
  | Gradient accumulation | 8             |
  | Maximum gradient norm | 1.0            |

## Final Testing
- The final testing script is in `evaluate.ipynb`.
- Includes code for soft matching and hard matching.
- Contains annotated sections for:
  - Quadruples
  - Triples
  - Pairs
  - Single elements

## Other Links
**Paper：** http://arxiv.org/abs/2501.15451v3

**Our dataset will be available on the Tianchi open evaluation platform. We welcome everyone to participate in discussions.**
https://tianchi.aliyun.com/competition/entrance/532298/informationhttps://tianchi.aliyun.com/competition/entrance/532298/information

## Poster
![poster_original](https://github.com/user-attachments/assets/c3cb7793-33f2-4e3e-ad72-e0d84530c658)

## Ethical Statement
**The ownership of the dataset belongs to the Information Retrieval Research Laboratory of Dalian University of Technology. The dataset contains examples of harmful and non-compliant content, which do not represent the stance of our team.**

**All resources are for scientific research purposes only and are strictly prohibited from commercial use.**
