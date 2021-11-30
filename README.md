# Machine-Transliteration

**Objective:** Develop an effective system for transliterating loanwords and named-entities across orthographically very different languages (In our case will focus on Transliteration from English to Hindi).

**Motivation:** In recent publications, authors have proposed a sequence to sequence (Seq2Seq) based Neural Machine Translation(NMT) framework for converting English statement to corresponding sentence in French, which have shown a high accuracy rate.

**Approach:** Seq2Seq model is used. A Seq2Seq model is an auto-encoder primarily consists of two parts i.e., an encoder for learning an intermediate representation and a decoder for generating target sequence from the intermediate representation.

**Models used for implementing Encoder & Decoder:** Long Short Term Memory (LSTM) and Bi-directional LSTM (Bi-LSTM)

**Implementation**

**Input:** Input contains two things

• Input text : English word 

• Target text : Hindi words

In order to train our model, we need to turn the words into 3 Numpy arrays, encoder_input_data, decoder_input_data, decoder_target_data:

• **encoder_input_data** is a 3D array of shape (num_pairs, max_english_sentence_length, num_english_characters) containing a one-hot vectorization of the English sentences.

• **decoder_input_data** is a 3D array of shape (num_pairs, max_Hindi_sentence_length, num_Hindi_characters) containg a one-hot vectorization of the Hindi sentences.

• **decoder_target_data** is the same as decoder_input_data but offset by one timestep. decoder_target_data[:, t, :] will be the same as decoder_input_data[:, t + 1, :].

**Output:** One-hot representation of characters in target language.
