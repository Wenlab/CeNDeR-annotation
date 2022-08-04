# CeNDeR-annotation
This toolkit can view and annotate whole brain imaging data.
## Human annotation and proofreading toolkit

Human annotation contains two main procedures: 

1. *Division*, convert raw tiff images into 3D image stacks

   ```matlab
   image_stack=import_micromanager_data_and_reshape;
   ```

   Read and divide tiff data according to your 3D imaging setup. The output should be a num_of_volumes × 1 *cell*. Each element of the *cell* is a volume, represented by a height × width × num_of_slices uint16 matrix. 

2. *Annotation*, draw and label bounding boxes manually; or proofread the inferred bounding boxes. This part runs in MATLAB. 

   - If you don't have bounding boxes :

     ```matlab
     whole_brain_imaging(image_stack)
     ```

     Show the image stack. To draw a bounding box by hand, select *Annotation->Bound neuron* in the menu bar, and then left-click to draw a rectangle in the GUI. To label a bounding box, select *Annotation->Assign index to outlier box* and left-click inside the bounding box.

   - If you have bounding boxes and want to proofread them:

     ```matlab
     whole_brain_imaging(image_stack, neuron_box)
     ```

     To correct the ID of a bounding box, select *Annotation->Assign index to outlier box* and then left-click inside the bounding box. 

   Select *File->Export* to save the bounding boxes to workspace and hard disk.
