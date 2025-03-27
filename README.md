# Bite-Sized-News-with-NLP-Automatically-Summarizing-CNN-Articles-Using-AI

#Introduction

In the age of information overload, news consumption can feel overwhelming. With thousands of articles published daily, it's easy to miss key stories—or worse, spend too much time trying to digest lengthy ones. Our project, "Bite-Sized News," leverages Natural Language Processing (NLP) to solve this. We built an AI-powered system that automatically summarizes CNN news articles into brief, informative insights.

# Dataset & Tools Used

Dataset:

CNN/DailyMail news dataset containing real-world news articles and summaries

Libraries: pandas (for data handling), matplotlib and WordCloud (for visualization)

Models: Gemini API, BART, and T5 (for abstractive summarization)

Metrics: ROUGE-1, ROUGE-2, ROUGE-L (for evaluation)


# Methodology

1. Data PreprocessingWe started by loading the dataset containing raw article text. The data was cleaned and structured using pandas. This included removing missing values and preparing the text data for analysis. Clean data ensures better performance in downstream tasks like summarization.
2. Word Cloud GenerationTo gain visual insight into the most frequently used terms in the dataset, we combined all article text and generated a word cloud. This provided an intuitive understanding of dominant themes and common topics within the articles.
3. Named Entity Recognition (NER)NER was implemented to identify and extract entities such as names of people, locations, and organizations. This step adds structure to the content and helps in understanding what or who the article is about, enriching the generated summaries with contextual relevance.
4. Abstractive SummarizationWe applied two methods for generating summaries:

    Transformer Models (BART and T5): These models were used to convert long articles into coherent and concise summaries. They are trained to generate new text that represents the main ideas of the input.

    Google Gemini API: Leveraged for its efficiency and fluency in generating human-like responses. It added diversity and richness to the summary generation.
  
5. Evaluation MetricsTo evaluate our summarization models, we used the ROUGE (Recall-Oriented Understudy for Gisting Evaluation) metric:
ROUGE-1: Measures unigram (word-level) overlap.
ROUGE-2: Measures bigram (two-word phrase) overlap.
ROUGE-L: Measures longest common subsequence, reflecting fluency and naturalness.
These metrics validated that our AI-generated summaries closely align with human-written ones in terms of content and structure.

# ROUGE Score Comparison: 

BART & T5 vs. GeminiA good ROUGE score for summarization models depends on the dataset and use case. 
Generally:
ROUGE-1: Should be around 0.4 to 0.5 for strong performance.

ROUGE-2: Should be around 0.15 to 0.25 for reasonable coherence.

ROUGE-L: Should be above 0.3 for fluency and structure retention.

Our evaluation produced the following results:

BART and T5

ROUGE-1: 0.3713

ROUGE-2: 0.1658

ROUGE-L: 0.3528

Gemini API

ROUGE-1: 0.2562

ROUGE-2: 0.0599

ROUGE-L: 0.2300


# Insights from the Results

BART & T5 outperformed Gemini across all ROUGE metrics, indicating better content retention and coherence.

Gemini produced more readable and fluent summaries but had lower precision and recall compared to BART & T5.

ROUGE-2 is significantly lower for Gemini (0.0599) compared to BART & T5 (0.1658), meaning Gemini struggles with bigram coherence in summaries.

BART & T5 maintain structured summaries while Gemini provides highly readable but sometimes less factually dense outputs.
