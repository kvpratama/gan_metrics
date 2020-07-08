# GAN Metrics

## Inception Score
Run `python inception_score.py --dataroot "path/to/image/folder"` to calculate IS

Because I use Pytorch ImageFolder class from torchvision.datasets, `path/to/image/folder` should contain folder of images. Please refer to the [documentation](https://pytorch.org/docs/stable/torchvision/datasets.html#imagefolder) for more detail.
```
path
└── to
    └── image
         └── folder
                └── class0
                        ├── 0.jpg
                        └── 1.jpg
                └── class1
                        ├── 0.jpg
                        └── 1.jpg
```

IS code is derived from [sbarratt](https://github.com/sbarratt/inception-score-pytorch)

## Fréchet Inception Distance
Run `python fid_score.py path/to/image/folder1 path/to/image/folder2 --gpu 0` to calculate FID. The `folder1` and `folder2` should contain images.

```
path
└── to
    └── image
         └── folder
                ├── 0.jpg
                └── 1.jpg
```


Option to calculate FID on multiple generated image folders. `python fid_score.py path/to/image/folder path/to/generated/folder --gpu 0 --multiple_gen_dir`. This command will output a summary file called `fid.csv`. Run this command to find the best FID epoch. 

```
path
└── to
    └── generated
         └── folder
                └── epoch0
                        ├── 0.jpg
                        └── 1.jpg
                └── epoch1
                        ├── 0.jpg
                        └── 1.jpg
```

IS code is derived from [mseitzer](https://github.com/mseitzer/pytorch-fid)