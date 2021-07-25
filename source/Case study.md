#  Case study

Program **case_study_pipeline.py** is used to generate RGB images and specified RGB thresholds to highlight gene marker areas. The RGB images and filtered images are stored in the ‘case_study’ sub-folders under specified output folder. Original 10X data files of S2-S17 samples and maker gene list can be found on [Link: ].

In ***case_study_pipeline.py***, these arguments are used:

## Required

- **-matrix** raw gene expression data provided by 10X in h5 file.
- **-csv** tissue positions provided by 10x in csv file.
- **-json** scale factors provided by 10x in json file.
- **-out** output folder 
- **-marker** gene list in a txt file recording marker genes in one column. If none, use all genes defaultly. [optional][default: None]
- **-method** embedding method: scGNN or spaGCN [default: scGNN]
- **-red_min** The lower limit of channel red [int]
- **-red_max** The upper limit of channel red [int]
- **-green_min** The lower limit of channel green [int]
- **-green_max** The upper limit of channel green [int]
- **-blue_min** The lower limit of channel blue [int]
- **-blue_max** The upper limit of channel blue [int]

## Optional

- **-pca** Whether to use PCA to reduce dimensions of gene expression. [optional] [default: True]
- **-transform** data pre-transformer: log, logcpm or None. [default: None]

If you want to obtain the **Fig4** results in the manuscript, you can run the following corresponding commands:
Figure4 b:

```python
python case_study_pipeline.py -matrix 10X/S4/S4_filtered_feature_bc_matrix.h5 -csv 10X/S4/spatial/tissue_positions_list.csv -json 10X/S4/spatial/scalefactors_json.json -out casestudy_4b -gene layer2+3.txt -method spaGCN -pca None -transform log -red_min 1 -red_max 88 -green_min 0 -green_max 101 -blue_min 1 -blue_max 113
```

Resept will return the following visuals:

![](pic1.png)![](pic2.png)



