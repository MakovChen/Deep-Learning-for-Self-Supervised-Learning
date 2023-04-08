

#### 2. Self-Attention機制
這個架構乍聽之下可以應用的範圍非常廣，而且也有助於實現許多更先進的應用。但是問題來了，既然每個輸入值的意涵是包括空間和時間資訊的，那我們到底該用甚麼方式進行正向傳播？全連結、卷積還是遞迴？答案都不是，Google在2017年就告訴了你[Attention Is All You Need [1]](https://arxiv.org/abs/1706.03762)，Self-Attention是一個透過該筆樣本中的其它輸入值來決定某個輸入值的神經元權重，概念上也有點像是對整個樣本進行卷積(空間資訊)，所以模型可以自主地選擇/過濾必要與不必要的資訊。

而這個模型也就是經典的Transformer模型，透過多個Encode和Decode Layer來處理長序列的歸納-生成問題。其中，一個Self-Attention Layer可以處理一個特定的觀點，多個Self-Attention就能處理多個觀點(例如：同一個單字有時用作名詞，有時則需要視為動詞)。而Positional Encoding就是為特徵添加位置資訊的技術，由於目前多數的應用仍是以離散型資料為主(整數型態)，因此根據位置添加一個三角函數小數便能代表它所在的位置，也使得這個模型可以處理時間資訊。所以就目前來看，連續型的輸入值和迴歸問題目前在這個架構上還無法使用。

#### 3. Transformer
![](https://i.imgur.com/z9HNI3Q.png)

Transformer編碼器，文字的意涵，遷移做其它應用
[[2] BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding](https://arxiv.org/abs/1810.04805)

### 序列式生成模型
Transformer解碼器
GPT-1
[[3] Improving Language Understanding
by Generative Pre-Training](https://cdn.openai.com/research-covers/language-unsupervised/language_understanding_paper.pdf)
GPT-2
[[4] Language Models are Unsupervised Multitask Learners](https://cdn.openai.com/better-language-models/language_models_are_unsupervised_multitask_learners.pdf)
GPT-3
[[5] Language Models are Few-Shot Learners
](https://arxiv.org/pdf/2005.14165.pdf)


# 透過PPO做Fine-tuning
