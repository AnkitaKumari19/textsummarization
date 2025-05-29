# textsummarization

from transformers import pipeline

summarizer = pipeline("summarization", model="facebook/bart-large-cnn")

input_text = input("Enter text to summarize:\n")

summary = summarizer(input_text, max_length=200, min_length=50, do_sample=False)

print("Summary:\n", summary[0]['summary_text'])
