# Data Preparation
## nuScenes
1. Download the offical nuScenes dataset data and map expansion [HERE](https://www.nuscenes.org/download).
2. We genetate custom info files which are different from mmdet3d's, which can be downloaded [HERE]().
## Argoverse
1. Download the official Argoverse 3D Tracking v1.1 [HERE](https://www.argoverse.org/av1.html#download-link).
2. We generate the argoverse info files, which can be downloaded [HERE]().

## OSM
1. Download osm data:
   - [boston-seaport]()
   - [singapore-hollandvillage]()
   - [singapore-queenstown]()
   - [singapore-onenorth]()
   - [Pittsburgh]()
   - [Miami]()
2. Generate raster tiles:
```bash
python projects/LocUtils/prepare_nusc.py ${PATH_TO_OSM_FILE} ${LOCATION}
# LOCATION = bs | son | shv | sq
python projects/LocUtils/prepare_argo.py ${PATH_TO_OSM_FILE} ${LOCATION}
# LOCATION = mia | pit
```
This will generate `tiles_{bs|son|sq|shv|mia|pit}_sd.pkl`.

### Folder structure
```
SegLocNet
├─ configs/
├─ mmdet3d/
├─ projects/
├─ tools/
├─ work_dirs/
├─ data
│    ├─ argoverse
│    │    ├─ test/
│    │    ├─ train1/
│    │    ├─ train2/
│    │    ├─ train3/
│    │    ├─ train4/
│    │    ├─ val/
│    │    ├─ argoverse_infos_test.pkl
│    │    ├─ argoverse_infos_train.pkl
│    │    ├─ argoverse_infos_val.pkl
│    ├─ nuscenes
│    │    ├─ maps/
│    │    ├─ samples/
│    │    ├─ sweeps/
│    │    ├─ v1.0-test/
│    │    ├─ v1.0-trianval/
│    │    ├─ nuscenes_infos_test_with_loc.pkl
│    │    ├─ nuscenes_infos_train_with_loc.pkl
│    │    ├─ nuscenes_infos_val_with_loc.pkl
│    ├─ osm
│    │    ├─ tiles_bs_sd.pkl
│    │    ├─ tiles_son_sd.pkl
│    │    ├─ tiles_sq_sd.pkl
│    │    ├─ tiles_shv_sd.pkl
│    │    ├─ tiles_mia_sd.pkl
│    │    ├─ tiles_pit_sd.pkl
```