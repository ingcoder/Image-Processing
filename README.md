# Image-Processing
## Load single image into pyplot

    #Import listdirectory function from OS module
    from os import listdir
    import pathlib
    import matplotlib.pyplot as plt
    import seaborn as sns
    import numpy as np
    import cv2

    #Retrieve filenames from directory
    file_list = pathlib.Path('images').glob('*/images/*.png')
    files = sorted([file for file in file_list])
    img_path = files[45]
    
    #read image
    img = cv2.imread(str(img_path))
    plt.imshow(img)
    plt.xticks([])
    plt.yticks([])

    print('Original image shape', img.shape)
    
    #transform to grayimage
    grayimg = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
    plt.imshow(grayimg, cmap='gray')
    print('New Image Shape',grayimg.shape)

![cell image](cell_image.png)

## Image Segmentation by Intensity Thresholding 

![cell image](histogram.png)

## Create seperate masks for each cell
![cell image](cell_seperation.png)

