# Fine-Tuning FLAN-T5 for News Summarization

I fine-tuned Google's FLAN-T5-small model on news articles to improve summarization quality. This was done using LoRA (Low-Rank Adaptation), which makes training way faster and more efficient.

## Results

Started with a baseline ROUGE-L score of 0.2216, and after fine-tuning got it up to 0.2373 - about 7% improvement. Not bad for training on just 100 examples!

## How to Run This

**[Open in Google Colab](https://colab.research.google.com/drive/1tt1WNLD6UQGFC6x85NeRaOGM4I2hzTYf?usp=sharing)**

Just click the link above, then run all cells in order. You'll get a Gradio demo link at the end to test the model.

## What I Did

- **Dataset**: XSum (BBC news articles)
- **Model**: FLAN-T5-small with LoRA
- **Training**: Tested 3 different hyperparameter configs
- **Best config**: Learning rate 5e-4, LoRA rank 8, trained for 2 epochs

The whole training took about 10 minutes on a free Colab GPU.

## Key Files

- `Fine_Tuning_Notebook.ipynb` - All the code for training and evaluation
- `requirements.txt` - Python packages needed
- `comparison_chart.png` - Visual comparison of results

## Why LoRA?

Instead of fine-tuning all 60 million parameters, LoRA only trains about 60,000 of them. This means:
- Much faster training (10 mins vs 40+ mins)
- Less memory needed
- Still gets good results

## What Could Be Better

With more time and resources, I'd:
- Train on the full dataset instead of just 100 examples
- Try a larger model (flan-t5-base)
- Run more training epochs
- Do proper human evaluation instead of just ROUGE scores

## Tech Stack

Built with Transformers, PEFT, Gradio, and the Hugging Face ecosystem.

---

**Kavin**
