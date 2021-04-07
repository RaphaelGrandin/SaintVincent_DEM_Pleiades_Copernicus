# SaintVincent_DEM_Pleiades_Copernicus
La Soufrière volcano (Saint Vincent) Fusion of Pleiades (2014, 2 m) and Copernicus (2018, 30 m) digital elevation models

# Authors

Raphaël GRANDIN<sup>1</sup> and Arthur DELORME<sup>2</sup>

1 : Université de Paris, Institut de Physique du Globe de Paris. Email: grandin@ipgp.fr

2: Université de Paris, Institut de Physique du Globe de Paris. Email: delorme@ipgp.fr

# 1. Collection Overview

This collection contains a digital surface model of the Soufrière volcano (Saint Vincent) calculated from Pleiades images acquired in 2014. Areas masked by clouds were filled using the Copernicus digital elevation model. The Pleiades dataset consists in three images acquired in 2014:

    * image A = DS_PHR1A_201407041445368_FR1_PX_W062N13_1009_00974 
    * image B = DS_PHR1A_201409271441564_FR1_PX_W062N13_1009_00974 
    * image C = DS_PHR1A_201410161445303_SE1_PX_W062N13_1009_00974

By combining these three images, three different digital surface models (DSMs) were computed (AB, BC and ABC). The three Pleiades DSMs were then merged together, keeping areas that are not masked by clouds. Areas that are not visible in any of the three DSMs due to clouds are subsequently filled with the Copernicus digital elevation model (DEM).

The collection includes four folders :

1. **Report**: 
    * "SaintVincent_DEM_Pleiades_Copernicus_fusion_Grandin_Delorme_2021.pdf": report
2. **DSM**: the merged DSM in Geotiff format:
    * "SaintVincent_Pleiades_Copernicus_merged.tif": the merged Pleiades DSM + Copernicus DEM
    * 
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
6. 

# Dataset Acknowledgement

Access to Pleiades data was granted through the DINAMIS program (https://dinamis.teledetection.fr/) via project ID 2021-055-Sci (PI: Raphaël Grandin, IPGP).
This work was supported by public funds received in the framework of GEOSUD, a project (ANR-10-EQPX-20) of the program “Investissements d’Avenir” managed by the French National Research Agency.
Calculation of the Pleiades DSM used the S-CAPAD cluster of IPGP.
