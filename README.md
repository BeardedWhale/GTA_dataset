# GTA_dataset
gta_crime_dataset

*Number of scenes*: 198

*Counter of videos*: Total: 961

Arrest: 134

Arson : 148

Assault: 107

Fight: 126

Vandalism: 105

Explosion: 158

Robbery: 48

Shooting: 140

## S3 bucket:
s3://gta-crime-dataset

# Steps:

1. clone repository, install requirements.txt
2. Register on aws, create account
3. configure aws cli: [instruction](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html) 
*AWS Access Key ID:* I will tell you when I will know your account ID
*AWS Secret Access Key:*  same
4. Now you can use dvc

# Dataset structure
For each class separate folder
```Fight   # any class name
├── 1      # scene number
│   ├── Fight1.mp4    # scene variants (angle, duration changes)
│   ├── Fight2.mp4
│   ├── Fight3.mp4
│   └── Fight4\ (2).mp4
├── 2
│   ├── Fight1.mp4
│   ├── Fight2.mp4
│   ├── Fight3.mp4
│   └── Fight4.mp4
├── 3
│   ├── Fight1_2A.mp4
│   ├── Fight2_2A.mp4
│   ├── Fight3_2A.mp4
│   ├── Fight5_2A.mp4
│   ├── Fight6_2A.mp4
│   └── Fight_204_2A.mp4
├── 4
│   ├── Cinema_20fight_202_2A.mp4
│   ├── Cinema_20fight_203_2A.mp4
│   ├── Cinema_20fight_204_2A.mp4
│   ├── Cinema_20fight_205_2A.mp4
│   ├── Cinema_20fight_206_2A.mp4
│   └── Cinema_20fighting_201_2A.mp4
├── 5
│   ├── Shop_20fight_201_2A.mp4
│   ├── Shop_20fight_202_2A.mp4
│   ├── Shop_20fight_203_2A.mp4
│   ├── Shop_20fight_204_2A.mp4
│   ├── Shop_20fight_205_2A.mp4
│   └── Shop_20fight_206_2A.mp4
└── 6
    ├── Fighting1_2A.mp4
    ├── Fighting_202_2A.mp4
    ├── Fighting_203_2A.mp4
    ├── Fighting_204_2A.mp4
    ├── Fighting_205_2A.mp4
    └── Fighting_206_2A.mp4
```

# DVC
Documentation: https://dvc.org

You do not need to do any configuration

## How to pull all data
1. dvc pull * -r s3remote
### pull only one class
2. dvc pull Fight.dvc

## How to add data
1. dvc add filename
2. dvc push -r s3remote
3. make sure that data is really loading to bucket
4. add recently created File.dvc, .gitignore  to git
5. push changes

## How to update existing data  (example )
1. dvc pull * (or particular file)
2. update folder with new videos
1. dvc update Fight.dvc (Class name)
2. dvc push -r s3remote


