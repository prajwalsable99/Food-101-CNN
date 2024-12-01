 # Food101 Image Classification & Nutritional Information App

This repository implements a food classification application using a pre-trained model on the **Food101 dataset**. The model classifies food images into 101 different categories and provides nutritional information for the predicted food. It uses TensorFlow's InceptionV3 model architecture and allows users to test food classification by providing images of food items.
![image](https://github.com/user-attachments/assets/1c92f31f-150f-4685-8929-3d47f524248b)

## Dataset Information

The **Food101 dataset** contains 101 food categories, each with 1,000 images, making it a total of approximately 100,000 images. The dataset is used to train a model to recognize different food items based on their visual features.

For more details on the dataset, you can visit the [Food101 Kaggle page](https://www.kaggle.com/datasets/dansbecker/food-101).

In this project, an additional CSV file is used to provide nutritional information for each dish:

- **dish**: Name of the food dish (e.g., apple_pie, pizza, etc.)
- **protein_per_100g**: Amount of protein in 100g of the dish
- **fats_per_100g**: Amount of fats in 100g of the dish
- **carbs_per_100g**: Amount of carbohydrates in 100g of the dish

## Project Structure



### Key Files
```
- **food-101.ipynb**: 
  - This notebook is used to train the food classification model. 
  - It loads the **Food101 dataset** and utilizes the InceptionV3 architecture to train a model to classify food items into one of 101 categories.
  - The final trained model is saved in the `inception_food101.h5` file.
  
- **food-app.ipynb**: 
  - This notebook is the main application used for classifying food images.
  - It loads the pre-trained model (`inception_food101.h5`), takes a user-uploaded image, classifies the food, and provides nutritional information based on the prediction.
  
- **food-nutrients.csv**: 
  - Contains nutritional details for each food item in the dataset, such as protein, fats, and carbohydrates per 100g. This data is used to display the nutritional values of the predicted food.
  
- **inception_food101.h5**: 
  - A saved version of the pre-trained food classification model based on the InceptionV3 architecture. The model was fine-tuned on the Food101 dataset and can classify food items when loaded.

- **images/**: 
  - A directory containing test images such as `donuts.jfif`, `chickenwings.jpg`, and others, used for testing the food classification model. You can add more images to test additional food items.
```
## How the Application Works

1. **Food Classification**:
   - The user uploads an image of food.
   - The application loads the pre-trained InceptionV3 model and classifies the food image into one of 101 categories (such as "pizza", "hamburger", "sushi", etc.).

2. **Nutritional Information**:
   - Once the food item is classified, the application fetches the nutritional data (protein, fats, carbs per 100g) from the `food-nutrients.csv` file.
   - Nutritional information for the predicted food item is displayed.

### Example Output

For example, when testing an image of donuts, the app outputs the following nutritional information:

Predicted Food: Donuts Nutrient Information for Donuts: Protein per 100g: 3g Fats per 100g: 17g Carbs per 100g: 70g


### Adding Your Own Images

You can add any image of food to the `images/` folder and test its classification. The app will display the predicted class and the corresponding nutritional information for the food item.

## Project Flow

### 1. **Dataset Preparation**:
   - **Food101 Dataset**: The Food101 dataset contains images and corresponding labels for 101 food categories. This dataset is used to train the classification model.
   - **Nutritional Data**: The `food-nutrients.csv` file provides nutritional information for each food item, which is retrieved based on the model's prediction.

### 2. **Model Training**:
   - **food-101.ipynb** is used for training the model. 
   - A pre-trained InceptionV3 model is used as a base, with additional custom layers added for food classification.
   - The model is trained on the Food101 dataset and saved as `inception_food101.h5`.

### 3. **Food Classification**:
   - **food-app.ipynb** is used to classify new food images. 
   - The user uploads an image, the model classifies the food item, and the app provides nutritional information from the `food-nutrients.csv` file.

### 4. **Testing**:
   - The application uses images stored in the `images/` folder to test the classification functionality. Additional images can be added for further testing.

## Requirements

To run this project, you'll need the following Python libraries:

- `tensorflow`
- `matplotlib`
- `numpy`
- `pandas`

