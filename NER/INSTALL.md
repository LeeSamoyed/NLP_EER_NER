## Instructions
1. create anaconda environment
    ```bash
    conda create -n YZS_NLP_NER python=3.6
    ```

2. datasets preparation
    ```bash
    # the path of datasets
    |--YZS_NLP
             |--NER
                  |--origin_data
                               |--relation2id.txt # relation
                               |--train.txt
                               |--test.txt
                               |--vec.txt
    ```

3. data format
	```bash
    # train & test
    word  label
    黄  B-PER
    卫  I-PER
    平  I-PER
    新  O
    著  O
    《  O
    中  B-LOC
    国  I-LOC
    政  O
    治  O
    体  O
    制  O
    改  O
    革  O
    纵  O
    横  O
    谈  O
    》  O
    ，  O
    已  O
    由  O
    中  B-ORG
    央  I-ORG
    编  I-ORG
    译  I-ORG
    出  I-ORG
    版  I-ORG
    社  I-ORG
    出  O
    版  O
    。  O
    # you can also see the format in origin_data-train.txt file
	```

4. environment
	```bash
    conda install tensorflow=1.12.0      # the version can not install too high  (>=1.0)
	```

5. main & test
    ```bash
    # Organize data into npy files, which will be save at data
    python initial.py

    # train
    python train_GRU.py

    # test
    python test_GRU.py
    ```

6. result
    ```bash
    # use about 80% of datasets (provided) for training and about 20% for testing
    epoch40
    accuracy:  90.66%; precision:  27.93%; recall:  21.93%; FB1:  24.57
    LOC: precision:  30.21%; recall:  44.62%; FB1:  36.02  96
    ORG: precision:  28.33%; recall:  15.74%; FB1:  20.24  60
    PER: precision:  17.39%; recall:   7.27%; FB1:  10.26  23


    # use about 100% of datasets (provided) for training and about 20% for testing
    epoch40
    accuracy:  99.55%; precision:  90.72%; recall:  91.88%; FB1:  91.30
    LOC: precision:  94.03%; recall:  91.30%; FB1:  92.65  67
    ORG: precision:  85.84%; recall:  88.99%; FB1:  87.39  113
    PER: precision:  96.49%; recall:  98.21%; FB1:  97.35  57
    ```