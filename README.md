# Hypo-Dense-Region-Segmentation
## Problem Statement
The objective of this hackathon challenge is to develop a robust and efficient algorithm or AI model capable of accurately segmenting the hypodense region from Brain Non-Contrast Computed Tomography (NCCT) images, regardless of the slice thickness and orientation of the images. The primary goal is to automate and streamline the identification of early ischemic changes in acute stroke patients.

## Data Description
In our project, we've assembled a dataset comprising `14 pairs of Nifti files`. These data are pivotal, enabling our deep-learning models to understand and predict brain structures effectively. Through meticulous curation, We've created a diverse collection that plays a foundational role in our journey to unravel the complexities of the human brain, bridging the realms of machine learning and neuroscience.

## Solution
For our solution, we harnessed the power of `Monai Framework` which also provides ease of implementation of UNET-3D deep learning architecture and other preprocessing parts, a sophisticated architecture tailor-made for tasks like ours. The `UNET-3D` ability to learn and represent intricate features within images was pivotal for our project's success.

To effectively train our algorithm, we judiciously split our dataset into three segments: a `70%` training set, a `15%` validation set, and another `15%` set aside for testing. Specifically, this translated to `10` images for training, `2` images for validation, and `2` images for rigorous testing. This allocation allowed us to both teach and evaluate our model's performance with rigor.

A critical step in our process was Preprocessing, where we carefully selected values and different preprocessing techniques to optimize our model's effectiveness. We employed a - `batch_size = 1`, which determined the number of images processed at once during training. We conducted training for the epoch `num_epochs = 30` – an iteration through the entire dataset.

This tailored approach, though constrained by computational availability, effectively allowed us to leverage the power of deep learning within our project. The outcome of these concerted efforts is a poised and well-equipped algorithm that holds promise for unraveling the mysteries concealed within the intricate structures of the human brain.

## Results
#### Training
During the training process, we utilized a dataset consisting of `10` original Nifti files paired with an equal number of corresponding mask images (Nifti files). In order to assess the performance of our model, we conducted validation using a separate set of 2 original nifti files along with their respective mask images. After it Following metrics we have achieved:-
<br>
- `Training data Metrics (metrics.txt)-- >` https://github.com/raunakkumar2110/Hypo-Dense-Region-Segmentation/blob/main/metrics.txt
- `Epoch_loss: 0.5123`
- `Epoch_metric: 0.4877`
- `val_loss_epoch: 0.5166`
- `val_dice_epoch: 0.4834`
- `current epoch: 30 current mean dice: 0.4802`
- `best mean dice: 0.4933 at epoch: 7`
- `train completed, best_metric: 0.4933 at epoch: 7`

There is a positive aspect to consider. Expanding the training process across multiple epochs holds the potential for a notable enhancement in accuracy. This prolonged training period would provide the model with a better opportunity to discern the nuanced relationships within the data, subsequently leading to a more adept prediction of masks for the original images. `It's also worth noting that computational resources (`GPU's`), an integral factor in training effectiveness, could have contributed to the limited initial dice score.`

#### Testing
Following the training phase, the subsequent crucial step involves testing. In this testing phase, we employed a set of 2 original Nifti Volume. The evaluation of our model on this test set yielded the following metrics:

-`Testing results.`
<br>
-` Testing data Metrics (metrics.txt) Click Here -- >`https://github.com/raunakkumar2110/Hypo-Dense-Region-Segmentation/blob/main/metrics.txt
- `Average Dice Score: 0.25190552519666287`
<br>
##### To Test the model There should be an input image (3D - .nii.gz) and its corresponding Mask image to be passed to the model. Kindly Read carefully the comments in the code for further assistance else there could be a chance of error.`

#### Prediction
`For prediction you need to check the file `Training-Testing.ipynb` file and give the path of a 3D .nii.gz Image file and also change the path acc to your system.`
-`Note: - I have utilized the dimensions `(128,128,28)` on Training Time and at Prediction Time just to check how the model works with different shapes we have the shape `(128,128,40)`
## Repository Structure 
- `requirements.txt`: The Libraries Need to be Installed with Specified Version to Avoid Version Errors.
- `output`: Contains the Graphs, and Predictions.
- `Model`: Contains the Model file (.pth) and metrics.
- `Dataset`: Different Training, Testing and Validation nifti files.
- `Training-Testing.ipynb`: Scripts to Train the Model And Test the Model`
- `preprocessing.ipynb`: Script for Preprocessing the NCCT.

