# GPT-2 - openAI

## Reference : 
Paper available [here](https://d4mucfpksywv.cloudfront.net/better-language-models/language_models_are_unsupervised_multitask_learners.pdf), blog post [here](https://blog.openai.com/better-language-models/), source code [here](https://github.com/openai/gpt-2)


## TL;DR 
OpenAi released recently (02/2019) a paper called *Language Models are Unsupervised Multitask Learners* which has been much debated because they use a complely unsupervised approach to build a **multi-task model**. This could be a small step toward Aritificial *General* Intelligence. But above all because they decided not to released the full trained model (only a smaller one) due to concern of missuse of the model.

## Paper Reading
The authors state that current NLP tasks (such as question answering, machine translation, reading comprehension, and summarization) are approached with supervised learning on task specific dataset (or unsupervised learning followed by supervised fine-tuning). In this paper they demonstrate that it is possible to build a huge model (1.5B parameters) on a huge dataset of raw texts (no labels) to achieve state of the art on some of the NLP tasks mentioned earlier. 

They demonstate that multi-task learning of large models is slower than superivsed learning but theoretically should have the same global minimum.

To reduce the size of the vocabulary, to avoid too much pre-processing and tokenization they prefer **a Byte Pair Encoding** instead of a Word-level encoding.

Their model is a **Transformer architecture** (Vaswani et al., 2017)

Their approach is a complete **zero-shot task transfer (no fine-tuning)**. As far as I have understood they only trained the model to **predict the next words** in a sentence given a seed to start. Thus the seed can whether be a full text in order to do a text summarization. Or question ending with question mark in order to be in the context of reading comprehension. Or english sentence ending with "=" to be in the context of english to french translation.   

At the end of the paper they also mentioned the problem of **Memorization**. Which occurs when there are overlapping text between training and test datasets which when training a model with such a large dataset can easily occur. They gave for each task a percentage of overlapping examples.

