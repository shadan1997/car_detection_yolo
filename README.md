# car_detection_yolo
# Detailed report summarizing 

**Task Objective:**
Train a YOLOv8 model to detect and classify objects from two classes, "car_norm" and "car_top_view," using a custom dataset.



Creating a Custom Dataset:

To create a custom dataset for object detection, we follow these steps:

1. Combining Two Datasets:

  We combine two existing datasets into a single dataset.
  - Dataset 1 contains aerial view images of cars.
  - Dataset 2 contains side view images of cars.
The combined dataset will be saved under the name 'car-dataset-yolo.'

2. Balancing the Dataset:
  - We observe that the combined dataset may have class imbalance issues, where one class (e.g., "aerial view") has more data than the other class (e.g., "side view").
To address this imbalance, we create a new balanced dataset.

3. Creating a Balanced Dataset:

  To create a balanced dataset, we take the following steps:

  * Data Selection:

  We randomly select a fixed number of images from each class in the combined dataset.
  For example, we choose 250 images of "aerial view" and 250 images of "side view."
  
  * Splitting Data:

  We split the selected data into two subsets: training and testing.
  Typically, we use an 80-20 split, where 80% of the selected data goes into the training set, and 20% goes into the testing set.

By creating a balanced dataset, you ensure that your model has an equal representation of both classes during training, which can lead to better model performance in object detection tasks.








# **Approach:**

1. **Data Collection:**
   - we have a custom dataset with two classes: "car_norm" and "car_top_view."
   - Each class contains 120 images for a total of 240 images.

2. **Data Splitting:**
   - You split the dataset into a training set (80%) and a validation set (20%).
   - The split resulted in 192 images in the training set and 48 images in the validation set.

3. **Model Selection:**
   - we chose to use YOLOv8, a state-of-the-art object detection model provided by the Ultralytics library.

4. **Hyperparameters:**
   - we set the following hyperparameters:
     - `imgsz`: Image size of 1280x1280 pixels.
     - `epochs`: Number of training epochs set to 30.
     - `batch`: Batch size set to 8 images per batch.
     - `name`: Model name as 'yolov8n_v8_50e'.

5. **Training:**
   - we loaded the pre-trained YOLOv8 model from 'yolov8n.pt.'
   - we trained the model using the custom dataset and specified hyperparameters.
   - The model was trained for 30 epochs.

6. **Challenges:**
  - Model Selection: The YOLO model is not able to detect cars in all orientations. To improve this, we need to train it with our data.
  - Dataset: Finding an appropriate dataset for our problem.
  - Data Imbalance: The dataset has an imbalance between the two classes, "car_norm" and "car_top_view," so we need to

7. **Results:**
   - The model was trained for 30 epochs, and the training and validation results can be examined to assess the model's performance.

