## Instructions
1. create anaconda environment
    ```bash
    conda create -n YZS_NLP_EER python=3.6
    ```

2. datasets preparation
    ```bash
    # the path of datasets
    |--YZS_NLP
             |--EER
                  |--data                             # training must (blank folder)
                  |--origin_data
                               |--relation2id.txt # relation
                               |--train.txt
                               |--test.txt
                               |--vec.txt
    ```

3. data format
	```bash
    # train & test
    entity_one  entity_two  relation  sentence
    同学	老师	师生	同学和老师是师生关系
    # you can also see the format in origin_data-train.txt file
	```

4. environment
	```bash
    conda install tensorflow=1.12.0      # the version can not install too high  (>=1.0)
    conda install scikit-learn
    conda install numpy=1.16.2           # the version can not install too high
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
    # because of the training dataset is not fit for the test dataset (provided), so the result is not good
    # and my CPU does not support me training to long and use large batch size
    # so I just use 100step for training and testing
    请输入中文句子，格式为 "实体一 实体二 句子":男人 女孩 男人的女儿是女孩
    实体1: 男人
    实体2: 女孩
    男人的女儿是女孩
    ```