Pipelines for "A dataset of images and morphological profiles of 30,000 small-molecule treatments using the Cell Painting assay", Bray et al. 2016 (http://dx.doi.org/10.5524/100200) 

Differences with (cellpainting_u2os_20x_imagexpress/analysis.cppipe)[https://github.com/broadinstitute/imaging-platform-pipelines/blob/master/cellpainting_u2os_20x_imagexpress/analysis.cppipe] are:

```
139,140c139,140
<     Size of smoothing filter:8
<     Suppress local maxima that are closer than this minimum allowed distance:8
---
>     Size of smoothing filter:20
>     Suppress local maxima that are closer than this minimum allowed distance:20
159c159
<     Lower and upper bounds on threshold:0.0125,1.0
---
>     Lower and upper bounds on threshold:0.0,1.0
197,198c197,198
<     Threshold correction factor:.8
<     Lower and upper bounds on threshold:0.02,1.0
---
>     Threshold correction factor:.9
>     Lower and upper bounds on threshold:0.003,1.0
```
