# Halil Yeşilağaç NlP Projesi
# English-Turkish-Machine-Translation_with_Seq2seq
Bu projede Seq2seq ile İngilizce'den Türkçe ye makine çevirisi uygulaması yaptım.İpynb adlı dosya uzantımda model kodlarım yer almaktadır. Aşağıda ve özet.doc dosyasında ayrıntılar bulunmaktadır.
Kullanılan Dataset:https://www.manythings.org/anki/


# Sequence-to-Sequence Architecture

Encoder: Processes English input (reversed) → generates context vector

Decoder: Generates Turkish tokens sequentially using context

# Key NLP Techniques

Tokenization:

Custom TokenizerWrap class with start (ssss)/end (eeee) markers

Sentence reversal for English inputs (improves short-term dependencies)

Padding to fixed length (11 tokens for EN, 10 for TR)

 # Embedding Layer

GloVe 100D vectors for English words (transfer learning)

Random initialization for Turkish words (94,058 unique tokens)

# Model Architecture


Encoder
Input → GloVe Embedding → 3x GRU(256) → Context Vector

Decoder
Input → Embedding → 3x GRU(256) → Dense(94,058) 
GRU 

Teacher forcing during training
# Training

Loss: Sparse Categorical Cross-Entropy

Optimizer: RMSprop (lr=1e-3)

Batch Size: 64


