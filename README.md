# Broad Imaging Platform pipelines

Cell Painting and other pipelines from the Imaging Platform.

## Guidelines for creating pipelines 

-**Note**: 
Each pipeline has two versions – one with `CreateBatchFiles` module enabled (named e.g. `analysis.cppipe`), and the other with the moduled disabled (named e.g. `analysis_without_batchfile.cppipe`). When updating the pipeline, ensure that these two versions are always in sync. 
The former is required by a [script](https://github.com/broadinstitute/cellpainting_scripts/blob/master/create_batch_files.sh) for creating CellProfiler batch files, which in turn are used to create a list of groups of images to be processed together, as well as Distributed-CellProfiler configuration files. The latter is used to run the pipeline using [Distributed-CellProfiler](https://github.com/CellProfiler/Distributed-CellProfiler/wiki).

2. The `ExportToSpreadsheet` module should always be configured with these values in order that the files are saved in a standard format and location
```
    Select the column delimiter:Comma (",")
    Add image metadata columns to your object data file?:No
    Limit output to a size that is allowed in Excel?:No
    Select the measurements to export:No
    Output file location:Default Output Folder\x7C
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

4. The `SaveImages` module should always be configured with these values in order that the files are saved in a standard format and location. The values shown for `Select image name for file prefix` and `Enter single file name` are specific for this example and should be adapted appropriately.

```
    Select image name for file prefix:OrigDNA
    Enter single file name:\\\\g<Well>_s\\\\g<Site>--nuclei_outlines
    Output file location:Default Output Folder sub-folder\x7Coutlines
    Overwrite existing files without warning?:Yes
```
