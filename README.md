## Fine tuning 3 models - Llama2, Mistral, and Phi2

### Model details:
- LLama2 [1] -> https://huggingface.co/NousResearch/Llama-2-7b-chat-hf
- Misral [2] -> https://huggingface.co/mistralai/Mistral-7B-v0.1
- Phi2 [3] -> https://huggingface.co/microsoft/phi-2

### Dataset used:
- alpace [4] -> https://huggingface.co/datasets/tatsu-lab/alpaca

### How to run?
- To run the notebook make sure to have access to GPU with high ram. Select the appropriate dataset partioning that you would wish to use to train and test the models. Change the parameters as needed. No further dependencies needed to be installed. (If required please uncomment the comments so that the needed dependencies will be installed.) Make sure to change the path for the output of the model.

### File descriptions:

**FineTuneLLama2_Assignment1C** -> Fine tuning LLama2 [1] using alpaca dataset [4]. 
**FineTuneMistral_Assignment1C** -> Fine tuning Mistral [2] using alpaca dataset [4]. 
**FineTunePhi2_Assignment1C(1)** -> Fine tuning Phi2 [3] using alpaca dataset [4]. 

**CalculateScoresForFineTunedModels** -> Genearte predictions using the testing set and evaluate them using 3 metrics: BLEU, ROUGE-L, and BERTScore. We also consider human evaluation (this is done by manually looking at the predictions. 

**CalculateScoresForFineTunedModels-DifferentTopKValues** -> Genearte predictions using the testing set but with hyperparameter changes (See Table [6] for more details). Evaluate them using 3 metrics: BLEU, ROUGE-L, and BERTScore. We also consider human evaluation (this is done by manually looking at the predictions. 


## Results 

The table below gives a overview of how the fine tuned models perform on text generation task. For prediction: two cases were considered. 
- First Case: Initial Prompt + Instruction
- Second Case: Initial Prompt + Instruction + Input

The generation were compared to the output column from the dataset (ground truth) 

| Model Name | BLEU | Rouge-L | BERTScore | Human Evaluation |
|:-------------|:--------------:|--------------:| --------------:|--------------:|
| Llama 2         | 0.07           | 0.21          | 0.84           | 0.70          |
| Phi 2    | 0.08      | 0.22     | 0.85           | 0.70          |
| Mistral    | 0.07      | 0.21     | 0.85           | 0.70          |


Overal results show that all the fine tuned models do almost similar in text generation task with the dataset (on overall average phi2 does do a minor better than the other two models). BLEU score is definitely not a good metrics for this task since the results are very low. BERTScores are relatively high since it works with semantic similarity. The generations/predictions are comprehendable by human beings so the human evaulation is relatively high. The generation of extra tokens affects all the models and their scores in repsonse to the metrics. 


### Hyperparameter Changes

### Top_k

| Model Name | Hyperparameters | BLEU | Rouge-L | BERTScore | Human Evaluation |
|:-------------|:--------------:|--------------:| --------------:|--------------:| :--------------:|
| Llama 2         | 3, 4, 5, 6           | 0.07, 0.06, 0.06, 0.07            | 0.21, 0.21, 0.20, 0.21              | 0,84, 0.84, 0.84, 0.84           | X          |
| Phi 2    | 3, 4, 5, 6      |  0.07, 0.06, 0.08, 0.07      | 0.20, 0.21, 0.22, 0.22            | 0.85, 0.85, 0.85, 0.85          | X          |
| Mistral    | 3, 4, 5, 6      | 0.06, 0.07, 0.06, 0.07      | 0.20, 0.21, 0.20, 0.21             | 0.84, 0.85, 0.84, 0.85           | X          |

### num_beams

| Model Name | Hyperparameters | BLEU | Rouge-L | BERTScore | Human Evaluation |
|:-------------|:--------------:|--------------:| --------------:|--------------:| :--------------:|
| Llama 2         | 6, 7, 8, 9           | X          | X           | X          | X          |
| Phi 2    | 6, 7, 8, 9      | X     | X           | X          | X          |
| Mistral    | 6, 7, 8, 9      | X     | X           | X          | X          |


### temperature

| Model Name | Hyperparameters | BLEU | Rouge-L | BERTScore | Human Evaluation |
|:-------------|:--------------:|--------------:| --------------:|--------------:| :--------------:|
| Llama 2         | 0.25, 0.45, 0.70, 0.95           | X          | X           | X          | X          |
| Phi 2    | 0.25, 0.45, 0.70, 0.95      | X     | X           | X          | X          |
| Mistral    | 0.25, 0.45, 0.70, 0.95      | X     | X           | X          | X          |


