The original (run) version of the analysis pipelines exported the `Object relationships.csv`; these were then removed by the command below before building the backends.  The pipline versions here do not export that CSV.

`aws s3 rm s3://imaging-platform/projects/2018_04_12_T2D_V2F_Saadat_Broad/workspace/analysis/2019_04_16_Batch1/ --recursive --exclude "*.*" --include "*/analysis/*/Object relationships.csv"`
