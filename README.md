XCR winning price prediction model
===

Detailed technical report of https://link.springer.com/chapter/10.1007%2F978-3-030-18590-9_43 DASFAA, 2019 is [here](https://github.com/paliwal90/xcr_win_price_pred/blob/master/xcr_wpp.pdf).

# Reproduce Results
Before starting Docker, if you are using docker-for-mac, please increase memory by going to 
```{Docker logo -> Preferences -> Advanced ->}.```
There default Memory should be 2GB. Increase this to atleast 10GB or more. 
CPU ~ 4 or more.

Then follow these steps:

## 1) Running docker container

```docker run -it abc123docker/xcr-winpp:latest bash```

The above command will first pull the docker image (for the first time). Then inside docker container, do the nexts:

## 2) Download ipinyou zip data

Download big ipinyou zip file, then process season 3 only. Season 2 is very huge.

```bash code/prepare_data/0-download_and_prepare_data.sh```

## 3) Preprocess

Example: first day of season 3

```Rscript code/prepare_data/1-initial_preprocessing.R 2013-10-19``` #YYYY-MM-DD

## 4) Model training

```python code/experiments/final_run.py 20131019``` #YYYYMMDD

## 5) Results

```data/prepared_data/simulated.20131019.result_all.txt```

