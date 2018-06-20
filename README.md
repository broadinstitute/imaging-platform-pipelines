# Broad Imaging Platform pipelines

Cell Painting and other pipelines from the Imaging Platform.

## Guidelines for creating pipelines

1. For each pipeline (e.g. `analysis.cpppipe`), always create a `without_batchfile` version of a pipeline (e.g. `analysis_without_batchfile.cpppipe`) and store in the same directory. The `without_batchfile` version is identical to the version without the suffix, except that the `CreateBatchFiles` module is disabled. The `without_batchfile` version exists because [Distributed-CellProfiler](https://github.com/CellProfiler/Distributed-CellProfiler) does not support the use of batch files. When updating the pipeline, ensure that these two versions are always in sync. 

1. The `LoadData` module should always be configured with these values in order that the load data CSV file can be specified on command line
```
    Input data file location:Elsewhere...\x7C
    Name of the file:
```
