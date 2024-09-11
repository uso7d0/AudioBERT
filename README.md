# AudioBERT
AudioBERT 📢 : Audio Knowledge Augmented Language Model

## Introduction
Language models like BERT, while powerful in text-based tasks, often lack auditory knowledge. This project introduces **AudioBERT**, a method to inject auditory knowledge into language models via a retrieval-based approach, improving performance on auditory knowledge tasks.  
To evaluate this, we introduce **AuditoryBench**, a dataset featuring tasks like animal sound recognition and sound pitch comparison. AudioBERT leverages **CLAP** (Contrastive Language-Audio Pretraining) for effective audio-text matching.

![AudioBERT_figure1_page-0001](https://github.com/user-attachments/assets/53e653a7-67ce-4b18-aaf0-45e3455c05f0)


## Dataset
### AuditoryBench
AuditoryBench is the first dataset aimed at evaluating language models' auditory knowledge. It comprises:
- **Animal Sound Recognition**: Predict the animal based on an onomatopoeic sound (e.g., "meow").
- **Sound Pitch Comparison**: Compare the pitch of different sound sources.

This dataset is built using audio-text pairs from the **LAION-Audio-630K** dataset and includes both training, development, and test sets. Further, we augment the data with audio from Wikipedia for broader generalization.

| Task                  | Train | Dev | Test | Wiki | Total |
|-----------------------|-------|-----|------|------|-------|
| Animal Sound Recognition | 4,211 | 593 | 1,211 | 197 | 6,212 |
| Sound Pitch Comparison  | 8,312 | 1,178 | 2,387 | 3,625 | 15,502 |

![AudioBERT_datapipline_figure2 (4)_page-0001](https://github.com/user-attachments/assets/aafac012-b7e0-49ed-9a33-e79217864d50)


## Model
### AudioBERT
AudioBERT uses a retrieval-based framework to inject auditory knowledge into language models. Its key components include:
- **Auditory Knowledge Span Detector**: Identifies relevant auditory spans in text.
- **CLAP**: Retrieves relevant audio embeddings from text spans.
- **LoRA (Low-Rank Adaptation)**: Dynamically adapts the model with auditory embeddings when necessary, ensuring general performance on other language tasks.

![AudioBERT_model (1)_page-0001](https://github.com/user-attachments/assets/1e8104c0-62ad-4d8a-8215-127c08e82023)

