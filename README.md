# Clickbait Classifier

Detecting clickbait in Indonesian news headlines, built for **Gemastik 2023** (Indonesia's national student tech competition). Four models — IndoBERT (fine-tuned transformer), XGBoost, Random Forest, and Naive Bayes — are trained and compared on the same task, with several data-augmentation strategies (deletion, insertion, substitution, swap) tested to squeeze more signal out of a modest labeled dataset.

## Results

| Model | Accuracy | Recall |
|---|---|---|
| **IndoBERT (fine-tuned)** | **0.83** | 0.30 |
| XGBoost / Random Forest / Naive Bayes | see [`model-results/classical-ml-scores.xlsx`](model-results/classical-ml-scores.xlsx) | |

IndoBERT was the best-performing model after fine-tuning and data augmentation. Full experiment logs for all 133 fine-tuning runs are on [Weights & Biases](https://api.wandb.ai/links/aigle-noir/dfjbhiej). Methodology, architecture notes, and the full write-up are in [`Paper.pdf`](Paper.pdf) and [`Catatan.pdf`](Catatan.pdf).

## Dataset

Built on **CLICK-ID**, a labeled dataset of Indonesian clickbait/non-clickbait headlines (William, A., & Sari, Y., *"CLICK-ID: A novel dataset for Indonesian clickbait headlines,"* Data in Brief, 32, 106231).

## Repo structure

- **`IndoBERT/`** — the core model.
  - `clean/` — preprocessed, augmentation-ready datasets and the main fine-tuning notebook.
  - `experiments-raw/` — the full experimentation trail: intermediate datasets, augmentation notebooks, and alternate fine-tuning runs (by title, by content, with/without augmentation).
- **`classical-ml-models/`** — XGBoost, Random Forest, and Naive Bayes baselines, plus the datasets used to train them.
- **`model-results/`** — evaluation scores for every model, used to compare approaches.
- **`Paper.pdf`** / **`Catatan.pdf`** — the write-up and architecture notes.

## Running it

1. Install dependencies for whichever model you're running (PyTorch + Transformers for IndoBERT; scikit-learn + XGBoost for the classical models).
2. Point the relevant notebook at a dataset from `IndoBERT/clean/datasets/` (IndoBERT) or `classical-ml-models/Dataset/` (classical models) — swap in a different augmented variant to compare.
3. Run the notebook to train, then evaluate against `model-results/` to compare against our reported scores.

## Credits

Built by Darrel Danadyaksa Poli, Edbert Halim, Patrick Samuel Evans Simanjuntak, and Andi Pujo Rahadi. Thanks to William & Sari for the CLICK-ID dataset.

## Citation

```bibtex
@misc{poli2024anda,
  title = {Anda Tidak akan Percaya Apa yang Dapat Diselesaikan Data Augmentation dalam Model Clickbait Classifier},
  author = {Darrel Danadyaksa Poli, Edbert Halim, Patrick Samuel Evans Simanjuntak, Andi Pujo Rahadi},
  year = {2024},
  month = {June},
  abstract = {Clickbait adalah artikel daring dengan judul menyesatkan yang sengaja dibuat untuk menarik pembaca untuk membuka halaman dari berita tersebut. Adanya unsur clickbait pada suatu judul berita dapat menyebabkan disinformasi pada masyarakat dengan minat membaca yang rendah. Penelitian ini bertujuan untuk membuat sebuah model untuk menentukan apakah suatu judul berita mengandung unsur clickbait atau tidak serta menguji model apa yang paling akurat untuk mendeteksi unsur clickbait yang ada pada suatu judul berita. Penelitian ini mengandung pengujian akurasi penentuan apakah suatu judul berita terindikasi mengandung clickbait atau tidak dengan menggunakan empat model, yaitu Indobert, XGBoost, Catboost, serta Naive-Bayes. Model paling akurat yang kami buat dan temukan adalah Indobert dengan accuracy score = 0.83 dan recall score = 0.3 setelah model IndoBERT melalui proses fine-tuning. Selain menggunakan IndoBERT, kami juga melakukan data augmentation pada penelitian ini untuk mencoba kemungkinan lain dalam membantu memperbanyak variasi data yang dapat digunakan.}
}
```
