# Text Conversational Model Selection using TOPSIS

Project Overview

The objective of this project is to **select the best pre-trained conversational (chat) model** using the **TOPSIS (Technique for Order Preference by Similarity to Ideal Solution)** method.  

Multiple pre-trained conversational models are evaluated on a dialogue dataset using different performance metrics.  
TOPSIS is then applied to rank the models and identify the best one.

---

Models Compared

The following pre-trained models from HuggingFace were used:

- microsoft/DialoGPT-small  
- microsoft/DialoGPT-medium  
- facebook/blenderbot-400M-distill  
- google/flan-t5-base  
- distilgpt2  

These models represent small, medium, and instruction-tuned conversational architectures.

---

Dataset Used

**Cornell Movie Dialog Corpus**

- Source: HuggingFace Dataset Library  
- Dataset contains real movie conversation dialogues  
- Input-response pairs were created from consecutive dialogue lines  
- 100 conversation pairs were used for evaluation to ensure fast execution

---

 Evaluation Metrics

Each model was evaluated using the following criteria:

| Metric | Description | Type |
|--------|-------------|------|
| BLEU Score | Measures similarity between generated reply and reference reply | Higher is better |
| Inference Time | Average time taken to generate a response | Lower is better |
| Model Size | Total number of parameters (in millions) | Lower is better |

These metrics form the **Decision Matrix** for TOPSIS.

---

Methodology

### Step 1: Loading the Dataset  
The Cornell Movie Dialog dataset was loaded using the HuggingFace `datasets` library.  
From the dataset, consecutive dialogue lines were paired to form input–response conversation samples.

### Step 2: Selecting Pre-trained Models  
Different pre-trained conversational models available on HuggingFace were chosen for comparison.  
Causal Language Models (like DialoGPT, GPT-2) and Seq2Seq models (like BlenderBot, FLAN-T5) were loaded separately according to their architecture.

### Step 3: Generating Model Responses  
Each model was given the same set of input sentences.  
For every input, the model generated a conversational reply.  
The time taken by each model to produce responses was recorded to measure inference speed.

### Step 4: Evaluating Model Performance  
The generated replies were compared with reference responses from the dataset.  
BLEU score was used to measure the similarity between generated and actual responses.  
Additionally, the total number of model parameters was calculated to represent model size.

### Step 5: Building the Decision Matrix  
All evaluation results (BLEU score, inference time, and model size) were organized into a decision matrix.  
This matrix served as the input for applying the TOPSIS method.

### Step 6: Applying TOPSIS  
The decision matrix was normalized and weighted based on the importance of each criterion.  
Ideal best and ideal worst solutions were identified.  
Finally, TOPSIS scores were calculated for each model and used to rank them.  
The model with the highest score was considered the best conversational model.

---


Results and Visualizations

The project generates:

- Evaluation metrics table (`topsis_conversational_results.csv`)  
- TOPSIS ranking bar graph (`topsis_ranking.png`)

<img width="1118" height="682" alt="image" src="https://github.com/user-attachments/assets/fd4eb23b-fdf1-4295-a62a-7461fcf99181" />

  
- Decision matrix heatmap
  
 <img width="770" height="529" alt="image" src="https://github.com/user-attachments/assets/11e311de-19c3-49ae-9048-1167a1d6000c" />


- Criteria correlation heatmap
  
<img width="882" height="572" alt="image" src="https://github.com/user-attachments/assets/46c726af-05ad-4729-a831-a0e4887ef7c9" />


- Pareto front plot
  
<img width="915" height="617" alt="image" src="https://github.com/user-attachments/assets/7a802369-131b-4545-b420-9993b8fa7c6e" />


- Sensitivity analysis plot

 <img width="969" height="662" alt="image" src="https://github.com/user-attachments/assets/664055b5-aa0e-4f3e-b14e-b106543308ff" />


These visualizations help in understanding model performance across different criteria.

---

Libraries Used

- Python  
- HuggingFace Transformers  
- HuggingFace Datasets  
- HuggingFace Evaluate  
- NumPy  
- Pandas  
- Matplotlib  
- PyTorch  

---

Conclusion

This TOPSIS-based approach offers a clear and structured way to compare and rank different conversational models using multiple evaluation criteria. The same methodology can easily be applied to other model selection or decision-making tasks by modifying the evaluation metrics, weights, and model choices.

---
 Author

**Satyam Gupta**  
ROllNO-102303729
---


