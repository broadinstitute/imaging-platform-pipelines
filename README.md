Cell Painting pipelines
==================

Cell Painting and other pipelines from the Imaging Platform.

- `cellpainting_a549_20x_phenix_bin1`- pipelines for processing Cell Painting images. The analysis pipeline was customized for A549 cells imaged at 20x on Opera Phenix, without binning. The illumination pipeline requires that the image dimensions are a multiple of 10 because it downsamples and upsamples by a factor of 10.
- `cellpainting_a549_20x_imagexpress` - pipelines for processing Cell Painting images. The analysis pipeline was customized for A549 cells imaged at 20x on ImageXpress, with binning. The illumination pipeline requires that the image dimensions are a multiple of 10 because it downsamples and upsamples by a factor of 10.


**Note:** The `without_batchfile` version of a pipeline is identical to the version without the suffix, except that the `CreateBatchFiles` module is disabled. The `without_batchfile` version exists because Distributed-CellProfiler currently does not support the use of batch files. When updating the pipeline, ensure that these two versions are always in sync. 

