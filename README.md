# Plant Leaf Disease Classification

A TensorFlow/Keras computer vision notebook for classifying plant-leaf images into 39 dataset categories, including healthy leaves and a background category.

[Open the notebook](Plant_Leaf_Disease_DL_Project.ipynb)

## Approach

- Load and extract the Mendeley plant-leaf image dataset.
- Split images by class into approximately 60% training, 20% validation, and 20% test sets.
- Resize images to 256 × 256 pixels and normalize pixel values.
- Augment training images with shear, zoom, and horizontal flips.
- Train a custom CNN with three convolutional layers, pooling, dense layers, and dropout for 10 epochs.
- Evaluate accuracy, weighted precision, recall, F1 score, and a confusion matrix.
- Save the model and weights and demonstrate single-image inference.

## Recorded results

These numbers are saved notebook outputs, not results independently reproduced for this README.

| Metric | Recorded value |
| --- | --- |
| Training images | 33,245 |
| Validation images | 11,098 |
| Test images | 11,105 |
| Classes | 39 |
| Test accuracy | 92.08% |
| Weighted precision | 0.93 |
| Weighted recall | 0.92 |
| Weighted F1 | 0.92 |

## Run in Google Colab

1. Open the notebook in Google Colab and select a GPU runtime if available.
2. Obtain the [original dataset](https://data.mendeley.com/datasets/tywbtsjrjv/1), following its access and license terms.
3. Place `Plant_leaf_diseases_dataset_without_augmentation.zip` in Google Drive, or update `zip_file_path` to your own location.
4. Check the extraction folder name and update `data_dir` if the archive structure differs.
5. Run the cells in order. Update the example inference paths to existing images in your test split.

The dataset and trained weights are not included in this repository. Runtime packages include TensorFlow, NumPy, Matplotlib, scikit-learn, Seaborn, and Pillow; the notebook also uses Colab's Drive integration. The original environment is not version-locked.

## Reproducibility and limitations

The split uses no fixed random seed, so fresh runs can produce different partitions and results. Use a clean output directory when splitting again: the current copying procedure does not clear previous splits. Save and reuse the training class-index mapping for inference instead of maintaining a separate label list.

The notebook demonstrates image classification and single-image inference; it does not include a deployed prediction API. Performance on this dataset does not establish accuracy on field photographs or unseen growing conditions.
