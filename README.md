Here's a comprehensive `README.md` for the VetMed model project based on the information you provided:

---

# VetMed Model

## Overview

The VetMed Model is a specialized generative pre-trained transformer (GPT) developed to address the gap in AI applications for veterinary medicine. While large language models (LLMs) have shown significant promise in human healthcare, the veterinary field has been underserved by AI advancements. The VetMed model aims to bridge this gap by providing a powerful tool tailored specifically for veterinary science, assisting in the initial diagnosis and first aid for animals, and enhancing the accessibility and quality of animal healthcare.

## Architecture

The VetMed model architecture is designed to be highly efficient and finely tuned for veterinary applications. Below is a visual representation of the model:

![VetMed Model Architecture](Untitled%20Diagram.drawio.png)

The model includes 32 layers, 32 attention heads, and a hidden size of 2048, designed to process complex veterinary data with high precision.

### Model Design

The VetMed model is designed with approximately 1 billion parameters, leveraging the Transformer architecture. The model includes the following features:

- **Hidden Size:** 2048
- **Intermediate Hidden Size:** 7168
- **Context Length:** 2048
- **Attention Heads:** 32
- **Layers:** 32
- **Vocabulary Size:** 32,000

### Advanced Features

- **Rotary Positional Embedding (RoPE):** This technique seamlessly incorporates positional information into the model, allowing it to better understand the sequential nature of veterinary texts.
- **Learnable Positional Encoding:** Enhances the model's ability to grasp the context within medical records and other veterinary documents.
- **RMSNorm & Layer Normalization:** These techniques significantly boost training stability by ensuring well-behaved gradient updates across layers.
- **Residual Connections:** Extensively used to prevent vanishing gradient problems, enabling the training of deep networks.
- **Dropout Layers:** Implemented between feedforward and attention layers to prevent overfitting.
- **SwiGLU Activation Functions:** Replace traditional ReLU activations, amplifying the model's ability to capture complex patterns in veterinary data.

### Attention Mechanisms

- **Grouped Query Attention:** Optimizes memory bandwidth consumption and enhances inference speed by efficiently processing information with 32 query attention heads and eight sets of key-value heads.
- **Adaptive Attention Span:** Dynamically adjusts the attention span based on context, improving overall model efficiency.

### Training Process

The VetMed model was trained on a machine equipped with six A100 GPUs over eight days. Key training details include:

- **Learning Rate:** 2e-4
- **Warm-up Steps:** 2000
- **Acceleration Technologies:** Fully Sharded Data Parallel (FSDP), FlashAttention, and Xformers were used to speed up the training process and optimize model performance.

## Dataset

The VetMed model was trained on a carefully curated dataset named VetMed, which comprises 500GB of data sourced from Wikipedia, Semantic Scholar Open Research Corpus (S2ORC), ArXiv, and RedPajama. The dataset includes:

- **Question-Answer Pairs:** Over 1 million QA pairs for fine-tuning and testing.
- **Multiple-Choice Question Pairs:** Approximately 16,340 MCQ pairs for fine-tuning.

## Results

The VetMed model demonstrated strong performance across various natural language processing tasks. Below is a summary of the evaluation results:

### ROUGE Score Comparison

| Model        | ROUGE-1_r | ROUGE-1_p | ROUGE-1_f | ROUGE-2_r | ROUGE-2_p | ROUGE-2_f | ROUGE-L_r | ROUGE-L_p | ROUGE-L_f |
|--------------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
| VetMed Model | 0.3251    | 0.0565    | 0.1324    | 0.05129   | 0.0132    | 0.0283    | 0.2688    | 0.1827    | 0.1197    |

These results indicate that the VetMed model performs reasonably well in aligning with reference texts, particularly in capturing longer sequences, although it still trails behind higher-performing models like Llama2 7B and Mistral 7B.

## Conclusion

The VetMed model represents a significant step forward in applying AI to veterinary medicine. While it shows promise, there is room for improvement, particularly in the model's logical reasoning capabilities and fine-tuning dataset quality. Future work will focus on enhancing the model's training datasets and broadening its exposure to a wider range of queries to further improve its accuracy and reliability in practical applications.


## Contact

For any questions or inquiries, please contact Sakshi Bennur at [sbennur@mail.yu.edu](mailto:sbennur@mail.yu.edu
