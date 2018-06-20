# Broad Imaging Platform pipelines

Cell Painting and other pipelines from the Imaging Platform.

## Guidelines for creating pipelines 

1. For each pipeline (e.g. `analysis.cpppipe`), always create a `without_batchfile` version of a pipeline (e.g. `analysis_without_batchfile.cpppipe`) and store in the same directory. The `without_batchfile` version is identical to the version without the suffix, except that the `CreateBatchFiles` module is disabled. The `without_batchfile` version exists because [Distributed-CellProfiler](https://github.com/CellProfiler/Distributed-CellProfiler) does not support the use of batch files. When updating the pipeline, ensure that these two versions are always in sync. 

1. The `LoadData` module should always be configured with these values in order that the load data CSV file can be specified on command line
```
    Input data file location:Elsewhere...\x7C
    Name of the file:
```

1. The `ExportToSpreadsheet` module should always be configured with these values in order that the files are saved in a standard format and location

```
    Select the column delimiter:Comma (",")
    Add image metadata columns to your object data file?:No
    Limit output to a size that is allowed in Excel?:No
    Select the measurements to export:No
    Output file location:Default Output Folder sub-folder\x7C
    Select source of sample row name:Metadata
    Select the image to use as the identifier:None
    Select the metadata to use as the identifier:None
    Export all measurement types?:Yes
    :
    Representation of Nan/Inf:NaN
    Add a prefix to file names?:No
    Filename prefix:
    Overwrite existing files without warning?:Yes
    Data to export:Do not use
    Combine these object measurements with those of the previous object?:No
    File name:
    Use the object name for the file name?:Yes
```
