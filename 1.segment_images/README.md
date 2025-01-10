This module segements the nuclei and cell.

# GIF Grid

| ![GIF 1](./examples/segmentation_output/nuclei_img_output.gif) | ![GIF 2](./examples/segmentation_output/cell_img_output.gif) |
|----------------------------|----------------------------|
| ![GIF 3](./examples/segmentation_output/nuclei_mask_output.gif) | ![GIF 4](./examples/segmentation_output/cell_mask_output.gif) |

For segmentation, we have found 3D too computationally expensive, yields less than optimal results, and/or did not work at all [errors in the code].
We have employed a 2.5D segmentation methodology in combination with Cellpose 2D segmentation.
For nuclei and cells, we take a sliding window of n z-slices, where we perform max-projection on these slides and perform segmentation on these slices; where n is the sliding window size.
We then decouple the max-projection to collect a segmentation mask per z-slice.
We then output the masks across all z-slices per image set as a stacked-TIFF file.

