## Fine tuning 3 models - Llama2, Mistral, and Phi2

### Model details:
- LLama2 -> https://huggingface.co/NousResearch/Llama-2-7b-chat-hf
- Misral -> https://huggingface.co/mistralai/Mistral-7B-v0.1
- Phi2 -> https://huggingface.co/microsoft/phi-2

### Dataset used:
- alpace -> https://huggingface.co/datasets/tatsu-lab/alpaca

### How to run?
- To run the notebook make sure to have access to GPU with high ram. Select the appropriate dataset partioning that you would wish to use t train and test the models. Change the parameters as needed. No further dependencies needed to be installed. (If required please uncomment the comments so that the needed dependencies will be installed.)

## Results 

The table below gives a overview of how the fine tuned models perform on text generation task. For prediction: two cases were considered. 
- First Case: Initial Prompt + Instruction
- Second Case: Initial Prompt + Instruction + Input

The generation were compared to the output column from the dataset (ground truth) 

| Model Name | BLEU | Rouge-L | BERTScore | Human Evaluation |
|:-------------|:--------------:|--------------:| --------------:|--------------:|
| Llama 2         | X           | X          | X           | X          |
| Phi 2    | X      | X     | X           | X          |
| Mistral    | X      | X     | X           | X          |


Overal results show that all the fine tuned models do almost similar in text generation task with the dataset (on overall average phi2 does do a minor better than the other two models). BLEU score is definitely not a good metrics for this task since the results are very low. BERTScores are relatively high since it works with semantic similarity. The generations/predictions are comprehendable by human beings so the human evaulation is relatively high. The generation of extra tokens affects all the models and their scores in repsonse to the metrics. 


### Hyperparameter Changes

### Top_k

| Model Name | Hyperparameters | BLEU | Rouge-L | BERTScore | Human Evaluation |
|:-------------|:--------------:|--------------:| --------------:|--------------:| :--------------:|
| Llama 2         | X           | X          | X           | X          | X          |
| Phi 2    | X      | X     | X           | X          | X          |
| Mistral    | X      | X     | X           | X          | X          |

### num_beams

| Model Name | Hyperparameters | BLEU | Rouge-L | BERTScore | Human Evaluation |
|:-------------|:--------------:|--------------:| --------------:|--------------:| :--------------:|
| Llama 2         | X           | X          | X           | X          | X          |
| Phi 2    | X      | X     | X           | X          | X          |
| Mistral    | X      | X     | X           | X          | X          |


### temperature

| Model Name | Hyperparameters | BLEU | Rouge-L | BERTScore | Human Evaluation |
|:-------------|:--------------:|--------------:| --------------:|--------------:| :--------------:|
| Llama 2         | X           | X          | X           | X          | X          |
| Phi 2    | X      | X     | X           | X          | X          |
| Mistral    | X      | X     | X           | X          | X          |
