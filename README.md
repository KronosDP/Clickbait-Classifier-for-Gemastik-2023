# Clickbait Classifier

## Overview

Welcome to the Clickbait Classifier project repository! This project is focused on detecting clickbait headlines in news articles and social media posts using a diverse set of machine learning models, including PyTorch-based IndoBERT, as well as XGBoost, Naive Bayes, and Random Forest.

## Dataset

For training and evaluating the classifiers, we utilize the "CLICK-ID" dataset, a valuable resource introduced by William, A., & Sari, Y. in their work titled "CLICK-ID: A novel dataset for Indonesian clickbait headlines" (Data in brief, 32, 106231). This dataset provides labeled examples of both clickbait and non-clickbait headlines in Indonesian text, playing a pivotal role in the success of our project.

## IndoBERT

The "IndoBERT" folder constitutes the core aspect of the project, wherein the powerful IndoBERT model is employed. IndoBERT is a pre-trained language model specifically designed for the Indonesian language.

### Clean IndoBERT Stuffs

This sub-folder contains meticulously organized resources related to IndoBERT.

- Datasets for IndoBERT: Here, you can find the datasets specifically tailored for IndoBERT. These datasets have undergone preprocessing and conversion into a suitable input format for fine-tuning. Additionally, we have applied data augmentation techniques, such as deletion, insertion, substitution, and swapping, to enhance the model's robustness.

### Dirty IndoBERT Stuffs

This sub-folder contains crucial resources from the IndoBERT model training process, such as logs and files generated during training and evaluation.

- WandB: [Weights & Biases](https://wandb.ai/) is utilized for experiment tracking and visualization, allowing us to monitor the training progress effectively.

  - Runs: Each sub-folder represents a distinct experiment run, identifiable by a unique identifier.

## XGBoost, Random Forest, Naive Bayes

In this folder, you can find the code pertaining to three traditional machine learning models employed for clickbait classification. We also provide catatan.pdf, which details the architecture used for the models.

### Dataset

This sub-folder contains the dataset used for training XGBoost, Random Forest, and Naive Bayes. Additionally, we have augmented the text data within this folder.

## Results

The "Hasil skor semua model" folder houses the evaluation scores and performance metrics for all the models trained during our experiments. These results are instrumental in comparing the effectiveness of different models, allowing us to identify the best-performing approach.

### Instructions to Run the Classifier

1. Ensure you have installed all the required dependencies.

2. Prepare the necessary datasets in the appropriate format for training. For the IndoBERT classifier, you can modify the dataset by changing its name. The same applies to the pre-trained model.

3. Execute the scripts or notebooks to train each model.

4. Utilize the trained models to make predictions on new clickbait headlines.

5. Evaluate the performance of your model alongside our model using the metrics provided in the "Hasil skor semua model" folder.

## Credits

We extend our gratitude to the creators of the "CLICK-ID" dataset, William, A., & Sari, Y., for their invaluable contribution to our project. Additionally, we acknowledge the usage of PyTorch, XGBoost, Naive Bayes, and Random Forest libraries in our implementation.

## Citation
```
@misc{poli2024anda,
  title = {Anda Tidak akan Percaya Apa yang Dapat Diselesaikan Data Augmentation dalam Model Clickbait Classifier},
  author = {Darrel Danadyaksa Poli, Edbert Halim, Patrick Samuel Evans Simanjuntak, Andi Pujo Rahadi},
  year = {2024},
  month = {June},
  abstract = {Clickbait adalah artikel daring dengan judul menyesatkan yang sengaja dibuat untuk menarik pembaca untuk membuka halaman dari berita tersebut. Adanya unsur clickbait pada suatu judul berita dapat menyebabkan disinformasi pada masyarakat dengan minat membaca yang rendah. Penelitian ini bertujuan untuk membuat sebuah model untuk menentukan apakah suatu judul berita mengandung unsur clickbait atau tidak serta menguji model apa yang paling akurat untuk mendeteksi unsur clickbait yang ada pada suatu judul berita. Penelitian ini mengandung pengujian akurasi penentuan apakah suatu judul berita terindikasi mengandung clickbait atau tidak dengan menggunakan empat model, yaitu Indobert, XGBoost, Catboost, serta Naive-Bayes. Model paling akurat yang kami buat dan temukan adalah Indobert dengan accuracy score = 0.83 dan recall score = 0.3 setelah model IndoBERT melalui proses fine-tuning. Selain menggunakan IndoBERT, kami juga melakukan data augmentation pada penelitian ini untuk mencoba kemungkinan lain dalam membantu memperbanyak variasi data yang dapat digunakan.}
}
```
