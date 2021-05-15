# Korean Honorific Neural Machine Translation

## Getting Started

### Step 1. Preprocess the data
```
!python preprocess.py
```
The source text file(`src`) and target text file(`tgt`)
default tokenize : `Mecab`+`SentencePiece`.

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

## License / 라이센스

This project is licensed under the MIT License - see the [LICENSE.md](https://gist.github.com/PurpleBooth/LICENSE.md) file for details / 이 프로젝트는 MIT 라이센스로 라이센스가 부여되어 있습니다. 자세한 내용은 LICENSE.md 파일을 참고하세요

## Reference
https://github.com/OpenNMT/OpenNMT-py
