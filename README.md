La Soufrière volcano (Saint Vincent) <br/>
Fusion of Pleiades (2014, 2 m) and Copernicus (2018, 30 m)<br/>
digital elevation models<a name="TOP"></a>
===================

## Authors

Raphaël GRANDIN<sup>1</sup> and Arthur DELORME<sup>2</sup>

1 : Université de Paris, Institut de Physique du Globe de Paris. Email: grandin@ipgp.fr

2: Université de Paris, Institut de Physique du Globe de Paris. Email: delorme@ipgp.fr


![](Figures/SaintVincent_Pleiades_Copernicus_IPGP_2021_V4.0.jpg?raw=true)


## 1. Collection Overview

This collection contains a digital surface model  (DSM) of the Soufrière volcano (Saint Vincent) calculated from Pleiades images acquired in 2014, hole-filled with the 2018 Copernicus digital elevation model (DEM).

The Pleiades dataset consists in three images acquired in 2014:

    * image A = `DS_PHR1A_201407041445368_FR1_PX_W062N13_1009_00974`
    * image B = `DS_PHR1A_201409271441564_FR1_PX_W062N13_1009_00974`
    * image C = `DS_PHR1A_201410161445303_SE1_PX_W062N13_1009_00974`

By combining these three images, three different digital surface models (DSMs) were computed (AB, BC and ABC). The three Pleiades DSMs were then merged together, taking advantage of the different cloud cover in the three pairs / triplets. Areas that are not visible in any of the three DSMs due to clouds are subsequently filled with the Copernicus DEM.

The collection includes five folders :

1. **Report**: 
    * "SaintVincent_DEM_Pleiades_Copernicus_fusion_Grandin_Delorme_2021.pdf": report
2. **DSM**: the merged DSM in Geotiff format:
    * "SaintVincent_Pleiades_Copernicus_merged.tif": the merged Pleiades DSM + Copernicus DEM
3. **Data**:  the three Pleiades DSMs in Geotiff format:
    * "SaintVincent_Pleiades_AB_dsm.tif": the Pleiades DSM computed from images A and B
    * "SaintVincent_Pleiades_AB_cor.tif": the correlation score betwen images A and B
    * "SaintVincent_Pleiades_BC_dsm.tif": the Pleiades DSM computed from images B and C
    * "SaintVincent_Pleiades_BC_cor.tif": the correlation score betwen images B and C
    * "SaintVincent_Pleiades_ABC_dsm.tif": the Pleiades DSM computed from images A, B and C
    * "SaintVincent_Pleiades_ABC_cor.tif": the correlation score betwen images A, B and C
4. **KMZ**: quickviews in KMZ format:
    * SaintVincent_Pleiades_Copernicus_merged_color.kmz": the merged Pleiades DSM + Copernicus
DEM in KMZ format (color version)
    * "SaintVincent_Pleiades_Copernicus_merged_shaded.kmz": the merged Pleiades DSM + Copernicus DEM in KMZ format (hillshade version)
5. **Figures**: the figures shown in the report 

## 2. Dataset Acknowledgement

Access to Pleiades data was granted through the DINAMIS program (https://dinamis.teledetection.fr/) via project ID 2021-055-Sci (PI: Raphaël Grandin, IPGP).

This work was supported by public funds received in the framework of GEOSUD, a project (ANR-10-EQPX-20) of the program "Investissements d’Avenir" managed by the French National Research Agency.

Calculation of the Pleiades DSM used the S-CAPAD cluster of IPGP.

## 3. Dataset Attribution

Dataset released under Creative Commons CC BY-NC 4.0 (Attribution-NonCommercial 4.0 International):
https://creativecommons.org/licenses/by-nc/4.0/

Attribution required for copies and derivative works:

> *The underlying dataset from which this work has been derived includes Pleiades material ©CNES (2014), distributed by AIRBUS DS, and EO material ©CCME (2018), provided under COPERNICUS by the European Union and ESA, all rights reserved.*
 
## 4. Dataset Citation

Grandin and Delorme (2021). “La Soufrière volcano (Saint Vincent) – Fusion of Pleiades (2014, 2 m) and Coperni- cus (2018, 30 m) digital elevation models”. Dataset distributed on Zenodo. https://doi.org/10.5281/zenodo.4660179.

```
@misc{grandindelorme2021,
title={{La Soufriere volcano (Saint Vincent) -- Fusion of Pleiades (2014, 2 m) and Copernicus
(2018, 30 m) digital elevation models}}, 
author={Grandin, Raphael and Delorme, Arthur},
year={2021},
howpublished={Dataset on Zenodo}, doi={10.5281/zenodo.4660179}
}
```

## 5. Collection Location

Country: Saint Vincent and the Grenadines

Bounding box:

```
<north>13.387947</north>
<south>13.293314</south>
<east>-61.106448</east>
<west>-61.244318</west>
```

## 6. Method
Three digital surface models (DSMs) are computed from panchromatic images from the Pleiades satellite, whose ground sampling distance (GSD) is 0.5 m. As no stereoscopic acquisition is available on the volcano area in the archive catalog, the processed images are monoscopic acquisitions, taken on three dates: 04/07/2014 (image A, [Figure 1](Figures/DS_PHR1A_201407041445368_FR1_PX_W062N13_1009_00974.png?raw=true)), 27/09/2014 (image B, [Figure 2](Figures/DS_PHR1A_201409271441564_FR1_PX_W062N13_1009_00974.png)) and 16/10/2014 (image C, [Figure 3](Figures/DS_PHR1A_201410161445303_SE1_PX_W062N13_1009_00974.png)). This dataset, with images of different dates, which are partially covered by clouds, is not ideal for producing a DSM. The idea is therefore to produce several DSMs with different combinations of images, then to merge these DSMs, finally filling any hole by interpolation or with an external DSM, namely the Copernicus DEM (https://spacedata.copernicus.eu/web/cscda/dataset-details?articleId=394198). Considering the base-to-height ratio of the different pairs of images, three combinations of images seem prone to provide satisfactory results: A-B, B-C and A-B-C.


Images are processed using the open source photogrammetry software MicMac (Rupnik et al., 2017)[https://opengeospatialdata.springeropen.com/articles/10.1186/s40965-017-0027-2]. First, the geometry model of each image is translated into MicMac format (`Convert2GenBundle` command). Then tie points between images are extracted from each possible pair of images (`Tapioca`). A bundle block adjustment is performed between the three images to refine the geometry models (`Campari`). Finally, the three DSMs are computed separately, by correlation between images A-B (1), B-C (2) and A-B-C (3) (`Malt`). The GSD of the DSMs is 0.5 m, thanks to MicMac multi-scale approach and regularization criterion. They are downsampled to 2 m to reduce the signal to noise ratio ([Figure 4a](Figures/AB_dsm_raw.png), [Figure 4c](Figures/BC_dsm_raw.png), [Figure 4e](Figures/ABC_dsm_raw.png)). Each DSM comes with a correlation score for each pixel, which can be used to remove pixels whose correlation score is below a certain threshold ([Figure 4b](Figures/AB_cor_raw.png), [Figure 4d](Figures/BC_cor_raw.png), [Figure 4f](Figures/ABC_cor_raw.png)).


The areas masked by clouds in the Pleiades DSM are then filled with the digital elevation model from Coper- nicus. A threshold on the correlation score is used to build a cloud mask. Finally, the three hole-filled DSMs are merged using the correlation score as a weighting factor ([Figure 5](Figures/Merged.png)).

## References

[1] Ewelina Rupnik, Mehdi Daakir, and Marc Pierrot Deseilligny. Micmac–a free, open-source solution for pho- togrammetry. Open Geospatial Data, Software and Standards, 2(1):1–9, 2017. [Link](https://opengeospatialdata.springeropen.com/articles/10.1186/s40965-017-0027-2)


