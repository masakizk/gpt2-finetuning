### Anaconda仮想環境作成
```shell
conda create -n gpt_rinna_finetuning python=3.7 anaconda
conda activate gpt_rinna_finetuning 
```

### Fine-tuning実行
```
!git clone https://github.com/huggingface/transformers -b v4.23.1
```

```
!python ./transformers/examples/pytorch/language-modeling/run_clm.py \
    --model_name_or_path=rinna/japanese-gpt2-medium \
    --train_file=train.txt \
    --validation_file=train.txt \
    --do_train \
    --do_eval \
    --num_train_epochs=3 \
    --save_steps=5000 \
    --save_total_limit=3 \
    --per_device_train_batch_size=1 \
    --per_device_eval_batch_size=1 \
    --output_dir=output/
```