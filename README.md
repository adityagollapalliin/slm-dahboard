# slm-dahboard
```
The 14B entry now uses the forensic values rather than assumptions: 14.77B parameters, 19,506 train / 198 validation samples, 3 epochs / 1,830 steps, LoRA r=32 α=64, effective batch 32, adamw_8bit, BF16 training, ~9.69 hours runtime, 1.176091 run-mean train loss, and 1.202948 best/final exported eval loss.

I also made the step-1200 vs step-1830 distinction explicit. The run completed normally at step 1830, but load_best_model_at_end selected checkpoint 1200, and that is what your exported adapter/merged model/GGUFs came from.

Updated dashboard

Download Medical SLM Dashboard v3

I also tested app.py; it launches successfully on:

http://127.0.0.1:7860

The updated dashboard now includes a dedicated Qwen2.5-14B Recovery tab with the full training-loss/eval-loss curve, learning-rate schedule, checkpoint comparison for 1200/1800/1830, best-checkpoint marker, final-training-step marker, and artifact-size comparison for the LoRA adapter, merged BF16 model, Q4_K_M GGUF, and Q8_0 GGUF.

I also updated the existing comparison pages so the 14B run appears alongside Qwen2.5-3B, Phi-4-mini, and DeepSeek-R1-Distill-Qwen-7B. GPU and VRAM remain intentionally blank for the 14B run because the forensic report confirmed they were never recorded.

The ZIP also contains the recovered source data under data/, including:

qwen14b_metrics.json
qwen14b_training_curve.csv
qwen14b_checkpoints.csv
qwen14b_forensic_report.md

So the dashboard is now preserving the evidence behind the 14B metrics rather than just hard-coding the values.
```
