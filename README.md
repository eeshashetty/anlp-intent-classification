# anlp-intent-classification
ANLP Project (Assignment 3) - Subjective acts and intents in conversational discourse
<br>
- Paper - https://arxiv.org/abs/2104.04470 <br>
- Baseline Code - https://github.com/elisaF/subjective_discourse/tree/master

# Recreating Baseline
We run existing Baseline code to retrieve results. There are minor updates to the code made for it to run on our system, and also to fetch data for analysis.

## Steps
1. Move into `baseline/hedwig`
2. Install Requirements
```
   pip install -r requirements.txt
```
3. To run Evaluation Code (RoBERTa Hierarchical + Annotator)
- If you do not have a checkpoint
   ```
   python -u -m models.bert_hier  --dataset CongressionalHearing --model-family roberta --model roberta-base --max-seq-length 512 --evaluate-dev --patience 40 --lr 3e-5 --warmup-proportion 0.1 --weight-decay 0.1 --batch-size 8 --epochs 30 --seed 1234 --metrics-json metrics_roberta_hierarchical_gold_sentiments_coarse_num_r_text_test.json --first-input-column 16 --use-second-input --second-input-column 2 
   ```
- If you have a checkpoint
     - Run the same command line as above, and add an additional parameter
  ```
  --trained-model PATH_TO_TRAINED_MODEL_WEIGHTS.pt
  ```
