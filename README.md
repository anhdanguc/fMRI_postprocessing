# Postprocessing fMRI timeseries

This package implements the postprocessing of fMRI timeseries that consists of the following steps:
- Normalization
- Band-pass filtering
- Global signal processing

## Requirements
Julia 1.1 or later
- Packages: PyCall, Statistics, DSP

Python 3.x
- Packages: nibabel

## Usage

```julia
julia> preprocessDataset( filename, 
                          src_path, 
                          dst_path, 
                          dataset, 
                          fs_dataset, 
                          [normalized=true], 
                          [BPFed=true], 
                          [togsr=true], 
                          [fpass=[0.009, 0.08])

```

Input:
- **filename** : the file name of the fMRI scan to be processed
- **src_path** : the path to the source folder containing the fMRI file
- **dst_path** : the path to the destination folder where the output will be saved
- **dataset** : the name of the dataset
- **fs_dataset** : the dictionary having the (key, value) as (dataset::String, signal_frequency::AbstractFloat)
- **normalized** (optional) : whether to conduct the normalization step. Default: true
- **BPFed** (optional) : whether to conduct the Band-pass filtering step. Default: true
- **togsr** (optional) : whether to conduct the Global Signal Processing step. Default: true
- **fpass** (optional) : the two cut-off frequencies in Hz of the Band-pass filter . Default [0.009, 0.08]  

Output:
- Postprocessed file saved in the folder specified by *src_path* that has the file name specified by *filename*
