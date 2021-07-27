# Run RESEPT

### predict tissue architecture without annotation

Run the following command line to generate RGB images from different embedding parameters, segmentation maps with top5 Moran's I and their Moran's I value.
Please download the corresponding pre-trained model from [click here for downloading data and model](https://bmbl.bmi.osumc.edu/downloadFiles/data_and_model/data_and_model.zip) and put it in the specified folder.

```
wget https://bmbl.bmi.osumc.edu/downloadFiles/RESEPT/RESEPT.zip 
unzip RESEPT.zip
python test_pipeline.py -matrix Demo/S13/S13_filtered_feature_bc_matrix.h5  -csv Demo/S13/spatial/tissue_positions_list.csv  -json Demo/S13/spatial/scalefactors_json.json -out Demo_result  -method scGNN  -transform logcpm -checkpoint Demo/checkpoint/S13_scGNN.pth
```

#### 
