## Evaluating models

### Setup
```
pip install -r requirements.txt
pip install -e .
```

### Evaluate
To evaluate a model we need to supply the config of the model and the evaluator. We will use `meta-llama/llama-3-70b` as the evaluator. Its config is placed in `src/alpaca_eval/evaluators_configs/alpaca_eval_vllm_llama3_70b_fn`.

Now you need to change the huggingface path of your finetuned model in `model_config` to load it for evaluation.

1. Here is how you evaluate a finetuned models with `meta-llama/llama-2-chat` as the base model. Before running the below command, in `src/alpace_eval/models/configs/llama-2-7b-chat-hf` change the `model_name` to the huggingface path of your `llama-2-chat` finetuned model.
```
# need a GPU for local models
alpaca_eval evaluate_from_model \
  --model_configs 'llama-2-7b-chat-hf' \
  --annotators_config 'alpaca_eval_vllm_llama3_70b_fn'   
```

2. Here is how you evaluate a finetuned models with `meta-llama/llama-3.1-instruct` as the base model. In `src/alpace_eval/models/configs/llama-3.1-8b-instruct` change the `model_name` to the huggingface path of your `llama-3.1-instruct` finetuned model.
```
# need a GPU for local models
alpaca_eval evaluate_from_model \
  --model_configs 'llama-3.1-8b-instruct' \
  --annotators_config 'alpaca_eval_vllm_llama3_70b_fn'   
```