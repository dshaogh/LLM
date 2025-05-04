# **LLM Benchmarking Report**

*danhua.shao@gmail.com*

---

## **Abstract**

Comparative Analysis of Gemma3, Llama3, Mistral, Qwen2.5, and Qwen3  
 (Tasks: BoolQ, SQuAD v1, SQuAD v2)

## **1\. Benchmark Overview**

We evaluated five leading open-source LLMs on three different datasets:

* **BoolQ** (Yes/No Question Answering)

* **SQuAD v1** (Answerable questions)

* **SQuAD v2** (Mix of answerable and unanswerable questions)

Metrics include **accuracy**, **false positives/negatives**, **correct/wrong answer rates**, and **inference time**.

---

## **2\. Results Summary**

### **BoolQ Benchmark**

| Model | Accuracy | False Positive | False Negative | Time |
| ----- | ----- | ----- | ----- | ----- |
| Gemma3 | 81% | 8% | 10% | 42s |
| Llama3 | 79% | 5.5% | 15.5% | 46s |
| Mistral | **86%** | 5% | 9% | 6m |
| Qwen2.5 | 83% | **1%** | 16% | 4m |
| Qwen3 | 81.5% | 2% | 16.5% | 1m |

![chart][BoolQ Benchmark.png]

**Best Accuracy**: *Mistral (86%)*  
 **Fastest Model**: *Gemma3 (42s)*  
 **Lowest False Positive**: *Qwen2.5 (1%)*

---

### **SQuAD v1 (Answerable) Benchmark**

| Model | Correct | Wrong | No Answer | Time |
| ----- | ----- | ----- | ----- | ----- |
| Gemma3 | 94% | 3.5% | 2.5% | 54s |
| Llama3 | 88.5% | 5% | 6.5% | 60s |
| Mistral | **95.5%** | 4% | **0.5%** | 53s |
| Qwen2.5 | 94% | **2.5%** | 3.5% | 60s |
| Qwen3 | 91.5% | 3% | 5.5% | 60s |

**![][image2]**

**Best Accuracy**: *Mistral (95.5%)*  
 **Lowest Wrong Rate**: *Qwen2.5 (2.5%)*  
 **Lowest No Answer Rate**: *Mistral (0.5%)*

---

### **SQuAD v2 (Answerable) Benchmark**

| Model | Correct | Wrong | No Answer | Time |
| ----- | ----- | ----- | ----- | ----- |
| Gemma3 | 79% | 17.5% | 3.5% | 44s |
| Llama3 | 77.5% | 18% | 4.5% | 60s |
| Mistral | 70% | 29.5% | **0.5%** | 2m |
| Qwen2.5 | 81.5% | **10%** | 8.5% | 60s |
| Qwen3 | **83%** | 13% | 4% | 2m |

**![][image3]**

**Best Accuracy**: *Qwen3 (83%)*  
 **Lowest Wrong Rate**: *Qwen2.5 (10%)*  
 **Lowest No Answer Rate**: *Mistral (0.5%)*

---

### **SQuAD v2 (Unanswerable) Benchmark**

| Model | Correct | Wrong | Time |
| ----- | ----- | ----- | :---- |
| Gemma3 | 30% | 70% | 46s |
| Llama3 | 35.5% | 64.5% | 60s |
| Mistral | 21% | 79% | 3m |
| Qwen2.5 | **64.5%** | 35.5% | 60s |
| Qwen3 | 50% | 50% | 2m |

**![][image4]**

**Best Accuracy**: *Qwen2.5 (64.5%)* is the most honest model  
 **Fastest Model**: *Gemma3 (46s)*

---

## **3\. Analysis & Key Insights**

* **Mistral** consistently achieved the **highest accuracy** on BoolQ and SQuAD v1, but at the cost of **longer inference time** (up to 6 minutes).

* **Qwen2.5** stands out as a **strong all-rounder**, especially in SQuAD v2 (general benchmark). It has the highest correct rate (64.5%) and **lowest false positives** in BoolQ.

* **Qwen3** improved on Qwen2.5 in the answerable portion of SQuAD v2 but lagged in the general benchmark.

* **Gemma3** offers **fast inference** across the board but performs slightly lower in accuracy than top performers.

* **Llama3** shows **stable but mid-tier performance**. It does not lead in any benchmark but stays close to Gemma3 in efficiency.

---

## **4\. Recommendations**

* If **accuracy** is the top priority and **inference time is not critical**, **Mistral** is the best option.

* If you need a **balance between speed and accuracy** (especially for production use-cases), **Qwen2.5** is highly recommended.

* **Gemma3** offers the best speed with acceptable accuracy for latency-sensitive applications where response time matters most.

* **Llama3** and **Qwen3** offer middle-ground performance but do not outperform **Qwen2.5** in key metrics.

---

## **5\. Suggested Next Steps**

* Consider deeper evaluation on **long-context QA** and **retrieval-augmented tasks (RAG)**, as models like Qwen2.5 and Mistral show promising trends.
