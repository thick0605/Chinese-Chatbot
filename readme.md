# Chinese Chatbot

Chinese chatbot based on tensorflow framework.

## Example
```
Q: 告訴他們一切都很好
A: 他們會很好的
```

## Result
  - Perplexity: 7.91
  - Correltion score: 0.62

## Requirement

  - Tensorflow
  - Numpy
  - Pickle

## Training
```
python train.py <path/to/training_data.txt>
```
### Training Data Format
One sentence per line.
Seperate each conversation with ```+++$+++```

```
今天天氣如何？
天氣很好
+++$+++
這禮拜六你有什麼計畫嗎？
去看場電影吧
那你呢？
+++$+++
```

## Testing
```
python3 model_seq2seq.py <path/to/testing_data.txt> <path/to/output.txt>
```

### Input Foramt
One sentence per line.
```
今天天氣如何？
晚上想吃什麼？
```

### Output Format
The answer corresponding the same line of the input file. 
One sentence per line.
```
天氣很好
便當吧
```

## Download Pre-trained Model
```
wget https://www.dropbox.com/s/zkg889gw39ricfr/chatbot.ckpt.data-00000-of-00001 -P model_file/
wget https://www.dropbox.com/s/hp2g8x9gt79c42h/chatbot.ckpt.index -P model_file/
wget https://www.dropbox.com/s/dwsqilewfilk31z/chatbot.ckpt.meta -P model_file/
```

## Model Parameters Setting
  - LSTM dimension: 3 layers, 512 neurons for each layer
  - Dictioinary size: 3000 characters
  - Embedding dimension: 512 neurons
  - Beam search size: 5
  - Decoder input: the groud truth (teacher forcing method)
  - Batch size: 200
  - Epoch: 30
  - Learning rate: 0.001
  - Optimizer: Adam
  - Max time step: 25
