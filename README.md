# OpenNMT based Korean Honorific Neural Machine Translation (NMT)


## How to use

### Step 1. Preprocess the data
```
!python preprocess.py
```
The source text file(`src`) and target text file(`tgt`) are tokenized through `Mecab`+`SentencePiece`.

### Step 2. Train the model
```
!python train.py
```
If you want to continue training the model, add `--train_from (model path)/model.pt` later.

### Step 3. Translate
```
!python translate.py -model data/model/model.pt -src data/src-test.txt -tgt data/tgt-test.txt -replace_unk -verbose -gpu 0
```

### Step 4. Scoring the model
```
!perl tools/multi-bleu.perl data/tgt-test.txt < data/pred.txt
```

### tep 5. Excute GUI
```
!pyhton gui.py
```
You have to change from `"data/src-test.txt"` to `"data/demo/KoreanTokenInput.txt"` of `translate_opts > --src` in `opts.py`
and `"data/pred.txt"` to `"data/demo/EnglishTokenOutput.txt"` of `translate_opts > --output`.

---

## Reference
https://github.com/OpenNMT/OpenNMT-py
