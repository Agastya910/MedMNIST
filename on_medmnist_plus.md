# How we generated the MedMNIST+ (the larger-size version of MedMNIST)

The data in MedMNIST+ corresponds one-to-one with that in MedMNIST (size 28x28 for 2D, 28x28x28 for 3D), with the only difference lying in the resolution of the images. In other words, the dataset splits (*i.e.* train, val, and test) and the sample indices are the same for MedMNIST and MedMNIST+. 

It is important to emphasize that for the data obtained through center-crop followed by resizing in MedMNIST, we use the same size for center-crop and subsequently resize to obtain the target resolution in MedMNIST+. 

We will describe the details of MedMNIST+, compared with MedMNIST. More details of MedMNIST can be found in our [paper](https://doi.org/10.1038/s41597-022-01721-8).

### PathMNIST
In MedMNIST, we resize the source images of 3×224×224 into 3×28×28. 

In MedMNIST+, for size 224x224, we utilize the source images directly; while for size 64x64 and 128x128, we resize the source images into the target size. 

### ChestMNIST
In MedMNIST, we resize the source images of 1×1,024×1,024 into 1×28×28. 

In MedMNIST+, for size 224x224, 128x128, and 64x64, we resize the source images into the target size. 

### DermaMNIST
In MedMNIST, the source images of 3×600×450 are resized into 3×28×28. 

In MedMNIST+, for size 224x224, 128x128, and 64x64, we resize the source images into the target size. 

### OCTMNIST
In MedMNIST, the source images are gray-scale, and their sizes are (384–1,536)×(277–512). We center-crop the images with a window size of length of the short edge and resize them into 1×28×28. 

In MedMNIST+, for size 224x224, 128x128, and 64x64, we center-crop the images with a window size of length of the short edge, and then resize the source images into the target size. 

### PneumoniaMNIST
In MedMNIST, the source images are gray-scale, and their sizes are (384–2,916)×(127–2,713). We center-crop the images with a window size of length of the short edge and resize them into 1×28×28. 

In MedMNIST+, for size 224x224, 128x128, and 64x64, we center-crop the images with a window size of length of the short edge, and then resize the source images into the target size. Note that after center-crop, the smallest size of the images is 127x127, and we upsample them to 128x128 and 224x224. 

### RetinaMNIST
In MedMNIST, the source images of 3×1,736×1,824 are center-cropped with a window size of length of the short edge and resized into 3×28×28. 

In MedMNIST+, for size 224x224, 128x128, and 64x64, we first center-crop the images with a window size of length of the short edge, and then resize the source images into the target size. 

### BreastMNIST
In MedMNIST, the source images of 1×500×500 are resized into 1×28×28. 

In MedMNIST+, for size 224x224, 128x128, and 64x64, we resize the source images into the target size. 

### BloodMNIST
In MedMNIST, the source images with resolution 3×360×363 pixels are center-cropped into 3×200×200, and then resized into 3×28×28. 

In MedMNIST+, for size 224x224, 128x128, and 64x64, we first center-crop the images into 3×200×200, and then resize the source images into the target size. 

### TissueMNIST
In MedMNIST, each gray-scale image is 32×32×7 pixels, where 7 denotes 7 slices. We obtain 2D maximum projections by taking the maximum pixel value along the axial-axis of each pixel, and resize them into 28×28 gray-scale images. 

In MedMNIST+, following the same procedure in MedMNIST, we obtain 2D maximum projections by taking the maximum pixel value along the axial-axis of each pixel, resulting in images of size 1x32x32. Then, for size 224x224, 128x128, and 64x64, we resize the source images into the target size. 

### Organ{A,C,S}MNIST
In MedMNIST, Hounsfeld-Unit (HU) of the 3D images are transformed into gray-scale with an abdominal window. We crop 2D images from the center slices of the 3D bounding boxes in axial/coronal/sagittal views (planes). The only diferences of Organ{A,C,S}MNIST are the views. The images are resized into 1×28×28 to perform multi-class classifcation of 11 body organs. 

In MedMNIST+, following the same procedure in MedMNIST, we crop 2D images from the center slices of the 3D bounding boxes in axial/coronal/sagittal views (planes). Then, for size 224x224, 128x128, and 64x64, we resize the source images into the target size. 

### OrganMNIST3D
In MedMNIST, the source of the OrganMNIST3D is the same as that of the Organ{A,C,S}MNIST. Instead of 2D images, we directly use the 3D bounding boxes and process the images into 28×28×28 to perform multi-class classifcation of 11 body organs. 

In MedMNIST+, we directly use the 3D bounding boxes and process the images into 64x64x64. 

### NoduleMNIST3D
In MedMNIST, we center-crop the spatially normalized images (with a spacing of 1mm × 1mm x 1mm) into 28×28×28. 

In MedMNIST+, to be consistent with the dataset in MedMNIST, we center-crop the spatially normalized images (with a spacing of 1mm × 1mm x 1mm) into 28×28×28, and then upsample them into 64x64x64.

### AdrenalMNIST3D
In MedMNIST, we calculate the center of adrenal and resize the center-cropped
64×64×64 volume into 28×28×28. 

In MedMNIST+, we calculate the center of adrenal and center-crop the image into 64×64×64.

### FractureMNIST3D
In MedMNIST, for each annotated fracture area, we calculate its center and resize the center-cropped 64×64×64 image into 28×28×28. 

In MedMNIST+, for each annotated fracture area, we calculate its center and center-crop the image into 64×64×64. 

### VesselMNIST3D
In MedMNIST, we fix the non-watertight mesh with PyMeshFix and voxelize the watertight mesh with trimesh into 28×28×28 voxels. 

In MedMNIST+, we fix the non-watertight mesh with PyMeshFix and voxelize the watertight mesh with trimesh into 64×64×64 voxels. 

### SynapseMNIST3D
In MedMNIST, for each labeled synaptic location, we crop a 3D volume of 1024×1024×1024 and resize it into 28×28×28 voxels. 

In MedMNIST+, for each labeled synaptic location, we crop a 3D volume of 1024×1024×1024 and center-crop it into 64×64×64 voxels. 