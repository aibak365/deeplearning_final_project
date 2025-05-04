# deeplearning_final_project
CNN_classifier on CIFAR10 dataset

## 📈 Evaluation and Performance Discussion

After implementing the improved CNN model (`MyNet`) and training it for **50 epochs** on the **CIFAR-10 dataset**, the model achieved an accuracy exceeding **85%** on the test set — a significant improvement over the baseline.

### 🔍 Why Is the Model Performing Well?

#### ✅ Residual Connections
The model includes a **skip connection** between the first two convolutional layers. This helps preserve the input features and supports **gradient flow**, making it easier to optimize deeper layers. Inspired by ResNet architectures, this allows the network to learn **incremental (residual) corrections** rather than completely new representations.

#### ✅ Batch Normalization
Each convolutional layer is followed by **batch normalization**, which standardizes the activations and reduces internal covariate shift. This stabilizes and accelerates training, allowing the model to converge faster and more reliably.

#### ✅ Data Augmentation
The training set uses **random cropping** and **horizontal flipping**, increasing the diversity of training examples. This leads to better generalization and robustness on unseen data.

#### ✅ Dropout Regularization
A **dropout** layer is placed before the final classification layers to reduce overfitting. By randomly dropping units during training, the network becomes less reliant on specific neurons and generalizes better.

#### ✅ Adaptive Global Average Pooling
Instead of using large fully connected layers, the model uses **global average pooling**, which dramatically reduces the number of parameters and focuses on the most informative features. This also lowers the risk of overfitting.

#### ✅ Deeper Architecture (But < 10 Layers)
While adhering to the constraint of having **fewer than 10 convolutional + fully connected layers**, the model uses depth efficiently by **increasing channel capacity** (from 64 to 512). This allows richer feature extraction without violating the assignment limits.

