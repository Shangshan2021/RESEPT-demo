# Evaluation of segmentation results

Program __evaluation_pipeline.py__ is used to evaluate the segmentation results. User submits 10X and the corresponding label file to generate the RGB images, the visuals with top5 ranking on Moran’s I and the corresponding values of the evaluation index such as ARI. These output files are stored in the ‘segmentation_evaluation’ sub-folders under specified output folder. Original 10X data files and label files of S2-S17 samples and pretrained models can be found on [Link：].

In __evaluation_pipeline.py__, these arguments are used:

## Required

- **-matrix**  raw gene expression data provided by 10X in h5 file.
- **-csv** tissue positions provided by 10x in csv file.
- **-json** scale factors provided by 10x in json file.
- **-out** output folder.
- **-method** embedding method: scGNN or spaGCN [default: scGNN]
- **-label** csv file path with cell barcodes in 1st column and their labels in 2nd column.
- **-checkpoint** pretrained checkpoint file in pth file



 ## Optional

- **-transform** data pre-transformer: log, logcpm or None. [default: None]



If you want to obtain the **Fig3** results corresponding to S2-S17 samples in the manuscript, you can run the following commands:

S14:

```python
python evaluation_pipeline.py -matrix 10X/S14/S14_filtered_feature_bc_matrix.h5  -csv 10X/S14/spatial/tissue_positions_list.csv  -json 10X/S14/spatial/scalefactors_json.json  -out S14_out  -method scGNN  -transform logcpm -label label_csv/S14.csv -checkpoint checkpoint/S14_scGNN.pth
```

Resept will return XXXXXX and the following visuals:







 

