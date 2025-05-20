# AlignMMBench: Evaluating Chinese Multimodal Alignment in Large Vision-Language Models (ACL' 25)

<font size=4><div align='center' > [[🍎 Project Page](https://alignmmbench.github.io/)] [[📖 arXiv Paper](https://arxiv.org/pdf/2406.09295)] [[📊 Dataset](https://huggingface.co/datasets/THUDM/AlignMMBench)]  </div></font>

<p align="center">
    <img src="./assets/index.png" width="96%" height="50%">
</p>

---

## 🔥 News

* **`2025.05.20`** 🌟 Our paper has been accepted to ACL 2025!

* **`2024.09.23`** 🌟 We provide the code, model, and data for evaluation!
* **`2024.06.14`** 🌟 We released AlignMMBench, a comprehensive alignment benchmark for vision language models!


## 👀 Introduce to AlignMMBench

AlignMMBench a multimodal alignment benchmark that encompasses both single-turn and multi-turn dialogue scenarios. It includes three categories and thirteen capability tasks, with a total of 4,978 question-answer pairs.

### Features

1. **High-Quality Annotations**: Reliable benchmark with meticulous human annotation and multi-stage quality control processes.

2. **Self Critic**: To improve the controllability of alignment evaluation, we introduce the CritiqueVLM, a ChatGLM3-6B based evaluator that has been rule-calibrated and carefully finetuned. With human judgements, its evaluation consistency surpasses that of GPT-4.
   
3. **Diverse Data**: Three categories and thirteen capability tasks, including both single-turn and multi-turn dialogue scenarios.

<img src="./assets/image_examples.png" width="100%" height="50%">

## 💻 Evaluate your model

**Step 0** 
Download AlignMMBench data from [here](https://huggingface.co/datasets/THUDM/AlignMMBench), and CritiqueVLM model file from [here](https://drive.google.com/file/d/1YiOs4Tmh_DfMsuYHb2Ij53lSud9XSpUJ/view).

**Step 1** 
Infer your model on AlignMMBench and get your model responses in `.jsonl` format like this:
```json
{"question_id": "00000000-0", "predict": "..."}
{"question_id": "00000000-1", "predict": "..."}
{"question_id": "00000000-2", "predict": "..."}
```

**Step 2** Clone this repository and install requirements.
```bash
https://github.com/wuyuhang05/AlignMMBench.git && cd AlignMMBench
pip install -r requirements.txt
```

**Step 3** Run CritiqueVLM evaluator in `evaluate.py`:
```bash
python evaluate.py --critic_model_path <critiqueVLM_path> --response_file <your_model_responses_path> --metadata_file <metadata_path> --save_path <path_to_save_detailed_evaluation_results>
```


## 📈 Results

<p align="center">
    <img src="./assets/leaderboard.png" width="96%" height="50%">
</p>

## License

The use of the dataset and the original videos is governed by the Creative Commons Attribution-NonCommercial-ShareAlike
4.0 International (CC BY-NC-SA 4.0) license, as detailed in the  [LICENSE](./LICENSE).

If you believe that any content in this dataset infringes on your rights, please contact us at **wuyuhang2022@gmail.com**, **wenmeng.yu@aminer.cn** to request its
removal.

## Citation

If you find our work helpful for your research, please consider citing our work.

```bibtex
@misc{wu2024alignmmbench,
      title={AlignMMBench: Evaluating Chinese Multimodal Alignment in Large Vision-Language Models}, 
      author={Yuhang Wu and Wenmeng Yu and Yean Cheng and Yan Wang and Xiaohan Zhang and Jiazheng Xu and Ming Ding and Yuxiao Dong},
      year={2024},
      eprint={2406.09295},
      archivePrefix={arXiv}
}
```