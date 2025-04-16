Chatbot research Cogniss:

Problems with research: Fine-tuning chatbot is actually relatively easy, as we have unsloth, Supervised Fine-tuning Trainer, .... But the big problem is preparing the dataset. In this repo there is a folder dataCollect, which can scrap the internet and get the data to make the dataset. How to use below:

-go to data (the one with scrapy.cfg)

-run the command: scrapy crawl arthritis

-wait for it to crawl and proceed the data pulled from their website

-put the folder content_files to process_data

-run chunk_text.py. This will clean the data and create chunks if not created

-run convert_chunks.py to get the json format for training (currently not the right format to use)

It can run through a website and make a folder with many text files, and then can turn them into a single jsonl file to fine tune. But this dataset is nowhere good. There are resources for creating the dataset like https://trelis.com/advanced-fine-tuning/, but I do not have the fund to access. 

CreatingModels is a folder which contains a jupyter notebook provide by MLX community for fine tuning deepseek and uploading that fine-tuned model to hugging face or keep it in local devices, which can be used via Ollama. This is for Mac users, as we use a different GPU(MLX). Fine-tuning on Windows is easier. But as mentioned before, fine-tuning requires good dataset which we currently do not have, so the chatbot will generate nonsensical answers. 

CreatingModels can be run by following the notebook. Change the model chosen if needed. The cat_data.csv is a file I had chatgpt generated, and convert into training dataset using python code. 

The solution for this: 
-Dedicating time and resources for creating the dataset. Many people take months to prepare their dataset. 
-Using RAG system.

ChatbotRAG is a RAG system, which take in data (pdf or text file), analyze them and provide answers. RAG is like when we ask a student (DeepSeek) to take a test, we allow him to use provided textbooks. And fine-tuning is we have him learn everything beforehand. It will take the files provided (I currently use 1 pdf and 2 text files to avoid too much info so my mac wont freeze. The files are those generated using dataCollect). The UI is made by Grok. It can give decent answers after analyzing the files.

-navigate to the folder then run the command streamlit run chatbot.py to run the chatbot.



