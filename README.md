## How to install
### Dependencies
#### Web Service
```
luarocks install https://raw.githubusercontent.com/benglard/htmlua/master/htmlua-scm-1.rockspec
luarocks install https://raw.githubusercontent.com/benglard/waffle/master/waffle-scm-1.rockspec
luarocks install json
```

## How to run
* training
```
th trainer.lua -save_every 1 -savefile seq2seq-new-wv650-rnn650 -dropout 0.5 -word_vec_size 650 -highway_layers 2 -use_chars 0 -use_words 1 -rnn_size 650 -gpuid 0 -checkpoint_dir cv  -seq_length 35 -batch_size 30 -data_dir data/conv -max_epochs 100
```
* generating next sequences given a sequence
```
th generator.lua -gpuid 0 -model cv/seq2seq-new-wv650-rnn650-xxxxxx.t7
```
