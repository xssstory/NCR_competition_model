## Download the data

Download the data from [https://drive.google.com/drive/folders/1Ci-KLHKk-yP-y5fWX4_cU8bA2fL_q76e?usp=sharing](https://)

You should construct the files as follows:

```
.
└── data
    ├── train_2.json
    ├── dev_2.json
    └── test_2.json
```

## Download a competition model

Download the best model of the competition from [https://bounty-package.s3.cn-northwest-1.amazonaws.com.cn/biendata/226371/haihua-gpu_ver5.tar.gz](https://)

## Evaluate the model on the test set

```sh
docker load < haihua-gpu_ver5.tar.gz
docker run --runtime=nvidia -v `pwd`/data:/app/data haihua_gpu_image_ver_5 -input data/test_2.json -output data/out.csv
```

The result will be saved in `data/out.csv`

you can access the model dicretly by

```
docker run -it --rm --entrypoint="/bin/bash" haihua_gpu_image_ver_5
```

