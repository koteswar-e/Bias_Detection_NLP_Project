# Bias_Detection_NLP_Project

YouTube Link : https://youtu.be/gDj7IBUxx4E

# Bias Detection and Mitigation in Pre-trained Language Models

## Introduction
Pre-trained language models like BERT and DistilBERT have revolutionized NLP by delivering state-of-the-art performance. However, these models often encode societal biases, leading to issues in applications such as recruitment and personalized healthcare. This study focuses on mitigating such biases using adversarial training with Gradient Reversal Layers (GRL) while maintaining task performance.

---

## Objectives
1. **Quantify Biases:** Measure the extent of bias in language models using benchmarks like StereoSet and CrowS-Pairs.
2. **Apply Adversarial Training:** Use GRL to suppress bias-inducing features while maintaining task performance.
3. **Analyze Residual Biases:** Evaluate the trade-offs between fairness and performance post-debiasing.

---

## Related Work
### Bias in NLP
- **Static Embeddings (e.g., word2vec, GloVe):** Capture and propagate societal biases.
- **Contextual Models (e.g., BERT, GPT):** Exhibit nuanced biases in tasks like coreference resolution and sentence completion.

### Existing Debiasing Techniques
1. **Data Augmentation:** Introduce balanced datasets to reduce bias.
2. **Representation Learning:** Remove bias components from embeddings.
3. **Adversarial Training:** Penalize the model for learning biased representations.

### Evaluation Frameworks
- **StereoSet:** Quantifies stereotypical and anti-stereotypical associations across multiple domains.
- **CrowS-Pairs:** Assesses contextual biases using aligned sentence pairs.

---

## Methodology
### Pre-trained Models
- **BERT:** Known for robust contextual embeddings and high performance.
- **DistilBERT:** A lightweight version of BERT, offering efficiency with comparable accuracy.

### Datasets
- **StereoSet:** Evaluates bias across gender, profession, race, and religion with ~17,000 examples.
- **CrowS-Pairs:** Focuses on nine bias categories with 1,508 sentence pairs.

### Adversarial Training Framework
- Uses **Gradient Reversal Layers (GRL)** to penalize bias-inducing features.
- Balances **task loss** and **adversarial loss** to ensure fairness and performance.

### Implementation Details
- **Tools:** PyTorch and Hugging Face Transformers.
- **Hyperparameters:** Learning rate (5e-5), batch size (16), epochs (5).
- **Platform:** NVIDIA T4 GPU on Google Colab.

---

## Experimental Results
### Quantitative Analysis
- EO and DP metrics showed limited improvements post-debiasing.
- StereoSet and CrowS-Pairs results indicate marginal changes in fairness.

### Qualitative Insights
- Effective in mitigating biases in gender and profession tasks.
- Residual biases remain in nuanced contexts.

---

## Discussion
1. **Fairness vs. Performance:** Achieved fairness with minimal accuracy loss but significant computational overhead.
2. **Dataset Limitations:** Current datasets lack diversity in non-English languages and intersectional biases.
3. **Scalability Challenges:** GRL-based training introduces complexities for larger models.

---

## Conclusion and Future Work
### Conclusion
- Adversarial training with GRL is effective for mitigating biases while preserving task performance.
- Residual biases and dataset limitations call for more robust approaches.

### Future Directions
1. Develop multilingual and intersectionally diverse datasets.
2. Extend debiasing methods to advanced models like RoBERTa and T5.
3. Design new metrics to detect subtle and intersectional biases.

---

## References
1. Bolukbasi, T., et al. (2016). *Man is to Computer Programmer as Woman is to Homemaker?* NeurIPS 2016.
2. Sheng, E., et al. (2019). *The Woman Worked as a Babysitter.* EMNLP-IJCNLP 2019.
3. Ravfogel, S., et al. (2020). *Null It Out: Debiasing Pre-trained Language Models.* ACL 2020.
4. Zhao, J., et al. (2018). *Gender Bias in Coreference Resolution.* ACL 2018.
5. Caliskan, A., et al. (2017). *Semantics Derived Automatically from Language Corpora.* Science 2017.
6. Elazar, Y., et al. (2018). *Adversarial Removal of Demographic Information.* NAACL 2018.

