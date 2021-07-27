## Data prepare

### 10x Visium data

 * HDF5 file: A file stores raw gene expression data.  
 * ‘tissue_positions_list’ file: A file stores tissue capturing information, row, and column coordinates information.
 * ‘scalefactors_json’ file: A file stores other information describing the spots’ characteristics.

### Annotation file

An annotation file recording cell barcodes and their annotations which is used in evaluating tissue architecture with annotations or customizing segmentation model. The first column of the file stores cell barcodes and the second column stores corresponding annotations. The file should be named as: [sample_name]_annotation.csv. 

### Model file

A pretrained model file.

### Data structure

For per-sample, use the following data structure:

```
    data_folder/
    |_[sample_name]/
    |      |__spatial/
    |      |    |__‘tissue_positions_list’ file
    |      |    |__‘scalefactors_json’
    |      |__HDF5 file
    |      |__annotation file: [sample_name]_annotation.csv (optional)
    |
    |_model/
    |      |__model file
```
