## Production pipelines 

### 1. Feature extraction pipelines
- `JUMP_illum_LoadData_v1.cppipe`
- `JUMP_segment_LoadData_v1.cppipe` : This is not necessary for data generation. It is useful for testing segmentation parameters across your dataset prior to running the analysis pipeline. It outputs an overlay image of the Nuclei and Cells objects identified using the segmentation parameters set in the pipeline overlaid on the input image.
- `JUMP_analysis_v2.cppipe` : Second version of the analysis pipeline with additional modules for special mitochondrial features, including EnhanceOrSuppressFeatures, Threshold, MorphologicalSkeleton, MeasureObjectSkeleton, MeasureObjectIntensityDistribution. Mito special features will contain either mito_skel or mito_tubeness in their name. 


### on-the-fly QC pipelines
- `JUMP_QC_Drag-and-Drop_v1.cppipe`: QC feature extraction pipeline with drag-and-drop functionality to load images in a quick way
- `JUMP_QC_LoadData_v1.cppipe`: QC feature extraction pipeline using LoadData module to load images in a systematic way
- `JUMP_QC_Plate-CV_v1.knwf`: Knime pipeline to visualize plate QC results 
- `JUMP_QC_Drag-and-Drop_Notes.docx`: Notes on how to run the complete on-the-fly QC. Also explained below and in a [demo](https://jjcloud.box.com/s/qlxp7o3bbp02yejvl318udd4ap5gotf1) (starting on minute 3:45)

To run the QC on-the-fly workflow:

- Prerequisites:
  - Download and install CellProfiler version 4.1.3 desktop client	
  - Download Knime [current version](https://www.knime.com/downloads)
    - Within Knime client, Install HCS Tools
  - Download the CellProfiler pipeline `JUMP_QC_Drag-and-Drop_v1.cppipe` from this repo
  - Download the Knime workflow `JUMP_QC_Plate-CV_v1.knwf` from this repo
- Run CellProfiler QC on-the-fly pipeline. Notes for most modules are documented within the pipeline notes, but in brief:
  - Drag your exported images folder(s) onto the Images module
  -	Set Output Folder
  - Check segmentation settings
    - Enter Test Mode
    - Run pipeline through the Identify* modules
    - Adjust threshold settings as necessary
  - Run full set of images
    - Ensure to turn off window display for faster processing (Window -> Turn off…)
- Run Knime and load Knime workflow
  - Open the CSV Reader “Top Line Per-Image” and set the File path
  
    ![Screenshot 2021-07-01 at 12 49 31](https://user-images.githubusercontent.com/57905348/124112665-cfa4ba80-da6a-11eb-84cd-87d4a103bea0.png)   
  - Open the CSV Reader “Top Line Per-Object” and set the File path
  
    ![Screenshot 2021-07-01 at 12 51 03](https://user-images.githubusercontent.com/57905348/124112851-08dd2a80-da6b-11eb-874c-51c18a488ab7.png) 
  - Run the workflow
  
    ![Screenshot 2021-07-01 at 12 51 47](https://user-images.githubusercontent.com/57905348/124113003-375b0580-da6b-11eb-8e2f-9551d43487a1.png)
  - Inspect the plots
    - Right-click the final nodes and select “View …”
