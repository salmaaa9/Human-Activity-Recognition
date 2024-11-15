# Human-Activity-Recognition
Link to dataset :  https://dphi-live.s3.eu-west-1.amazonaws.com/dataset/Human+Action+Recognition-20220526T101201Z-001.zip
1. Loading Dataset and CSV Files:
Paths to the training and testing images are specified.
The CSV files that contain the labels (Training_set.csv, Testing_set.csv) are read using pandas.
2. Dataset Exploration:
Displaying the first few rows of the training dataset and checking for missing values, duplicates, and dataset statistics.
From the output, there are 12,600 records, and no missing or duplicate values.
3. Visualizing Sample Images:
Images from different classes are displayed in a 3x5 grid to give an overview of the dataset.
A histogram of the class distribution is generated to show that there is no class imbalance.
4. Outlier Detection (Z-Score Method):
Using the z-score method, the dataset is checked for outliers, and the result shows that there are no rows with outliers in the numerical data.
5. Image Intensity Distribution:
A pixel intensity histogram for grayscale images is plotted, showing that most pixels have lower intensity values, with a significant peak near the maximum intensity (indicating possibly bright areas in the images).
Z-scores of pixel intensities are calculated to detect outlier pixels, which result in zero outliers.
6. Edge Intensity Distribution:
The Sobel edge detection filter is applied to the images, and a histogram of mean edge intensities is plotted.
The distribution shows that most images have low to moderate edge intensity, indicating relatively smooth regions in the dataset.
7. Data Augmentation:
Data augmentation is applied to the training images using transformations like resizing, random horizontal flips, rotations, and color jittering to improve the diversity of the training data.
Validation images are resized but not augmented (no transformation applied).
8. Custom Dataset Class and DataLoader:
A custom PyTorch dataset class (CustomImageDataset) is defined to load the images and their labels, with optional transformations applied to the images.
The training and validation sets are split, and DataLoader objects are created for both the training and validation datasets.
9. Visualizing Transformed Images:
A batch of transformed training images is visualized using torchvision.utils.make_grid to confirm the transformations are being applied correctly.
