Model 00:
\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_
Layer (type) Output Shape Param \#
================================================================= conv2d
(Conv2D) (None, 28, 28, 2) 56

flatten (Flatten) (None, 1568) 0

dense (Dense) (None, 43) 67467

================================================================= Total
params: 67,523 Trainable params: 67,523 Non-trainable params: 0

conv2d: 2 filters, (3, 3) kernel, activation = relu dense: 43 neurons,
activation = sigmoid

Time taken: 1s/epoch loss: 0.0456 accuracy: 0.7437

Model 01:

Changes: Changed conv2d activation from relu to sigmoid
\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_
Layer (type) Output Shape Param \#
================================================================= conv2d
(Conv2D) (None, 28, 28, 2) 56

flatten (Flatten) (None, 1568) 0

dense (Dense) (None, 43) 67467

================================================================= Total
params: 67,523 Trainable params: 67,523 Non-trainable params: 0

conv2d: 2 filters, (3, 3) kernel, activation = sigmoid dense: 43
neurons, activation = sigmoid

Time taken: 796ms/epoch loss: 0.0172 accuracy: 0.9086

Result: Improved time and accuracy

Model 02:

Changes: Changed dense activation from sigmoid to relu

------------------------------------------------------------------------

Layer (type) Output Shape Param \#
==================================

conv2d (Conv2D) (None, 28, 28, 2) 56

flatten (Flatten) (None, 1568) 0

dense (Dense) (None, 43) 67467

================================================================= Total
params: 67,523 Trainable params: 67,523 Non-trainable params: 0

conv2d: 2 filters, (3, 3) kernel, activation = sigmoid dense: 43
neurons, activation = relu

Time taken: 801ms/epoch loss: 0.1341 accuracy: 0.0922

Result: Abysmal

Model 03:

Changes: Changed filter value of conv2d from 2 to 8

------------------------------------------------------------------------

Layer (type) Output Shape Param \#
==================================

conv2d (Conv2D) (None, 28, 28, 8) 224

flatten (Flatten) (None, 6272) 0

dense (Dense) (None, 43) 269739

================================================================= Total
params: 269,963 Trainable params: 269,963 Non-trainable params: 0

conv2d: 8 filters, (3, 3) kernel, activation = sigmoid dense: 43
neurons, activation = sigmoid

Time taken: 742ms/epoch loss: 0.0091 accuracy: 0.9634

Result: Improvement from Model 01

Model 04:

Changes: Changed filter value of conv2d layer from 8 to 16

------------------------------------------------------------------------

Layer (type) Output Shape Param \#
==================================

conv2d (Conv2D) (None, 28, 28, 16) 448

flatten (Flatten) (None, 12544) 0

dense (Dense) (None, 43) 539435

================================================================= Total
params: 539,883 Trainable params: 539,883 Non-trainable params: 0

conv2d: 16 filters, (3, 3) kernel, activation = sigmoid dense: 43
neurons, activation = sigmoid

Time taken: 902ms/epoch loss: 0.0056 accuracy: 0.9824

Result: Improvement from Model 03. Slower but more accurate.

Model 05:

Changes: Added a dense layer

------------------------------------------------------------------------

Layer (type) Output Shape Param \#
==================================

conv2d (Conv2D) (None, 28, 28, 16) 448

flatten (Flatten) (None, 12544) 0

dense (Dense) (None, 86) 1078870

dense\_1 (Dense) (None, 43) 3741

================================================================= Total
params: 1,083,059 Trainable params: 1,083,059 Non-trainable params: 0

conv2d: 16 filters, (3, 3) kernel, activation = sigmoid dense: 86
neurons, activation = relu dense\_1: 43 neurons, activation = sigmoid

Time taken: 1s/epoch loss: 0.0094 accuracy: 0.9676

Result: Slower and less accurate.

Model 06:

Changes: Changed dense layer activation from relu to sigmoid

------------------------------------------------------------------------

Layer (type) Output Shape Param \#
==================================

conv2d (Conv2D) (None, 28, 28, 16) 448

flatten (Flatten) (None, 12544) 0

dense (Dense) (None, 86) 1078870

dense\_1 (Dense) (None, 43) 3741

================================================================= Total
params: 1,083,059 Trainable params: 1,083,059 Non-trainable params: 0

conv2d: 16 filters, (3, 3) kernel, activation = sigmoid dense: 86
neurons, activation = sigmoid dense\_1: 43 neurons, activation = sigmoid

Time taken: 1s/epoch loss: 0.1044 accuracy: 0.0542

Result: Abysmal

Model 07:

Changes: Removed dense layer, changed conv2d kernel from (3, 3) to (6,
6)

------------------------------------------------------------------------

Layer (type) Output Shape Param \#
==================================

conv2d (Conv2D) (None, 25, 25, 16) 1744

flatten (Flatten) (None, 10000) 0

dense (Dense) (None, 43) 430043

================================================================= Total
params: 431,787 Trainable params: 431,787 Non-trainable params: 0

conv2d: 16 filters, (6, 6) kernel, activation = sigmoid dense: 43
neurons, activation = sigmoid

Time taken: 867s/epoch loss: 0.0094 accuracy: 0.9599

Result: Faster but less accurate compared to model 04

Model 08:

Changes: Removed dense layer, changed conv2d kernel from (6, 6) to (1,
1)

------------------------------------------------------------------------

Layer (type) Output Shape Param \#
==================================

conv2d (Conv2D) (None, 30, 30, 16) 64

flatten (Flatten) (None, 14400) 0

dense (Dense) (None, 43) 619243

================================================================= Total
params: 619,307 Trainable params: 619,307 Non-trainable params: 0

conv2d: 16 filters, (1, 1) kernel, activation = sigmoid dense: 43
neurons, activation = sigmoid

Time taken: 869s/epoch loss: 0.0131 accuracy: 0.9342

Result: Faster but less accurate compared to model 04

Model 09:

Changes: Reverted conv2 kernel to (3, 3), changed filter from 16 to 32

------------------------------------------------------------------------

Layer (type) Output Shape Param \#
==================================

conv2d (Conv2D) (None, 28, 28, 32) 896

flatten (Flatten) (None, 25088) 0

dense (Dense) (None, 43) 1078827

================================================================= Total
params: 1,079,723 Trainable params: 1,079,723 Non-trainable params: 0

conv2d: 32 filters, (3, 3) kernel, activation = sigmoid dense: 43
neurons, activation = sigmoid

Time taken: 1s/epoch loss: 0.0088 accuracy: 0.9645

Result: Faster but less accurate compared to model 04

Conclusion: Model 04 is the best version Adding a layer makes it a worse
16 filters and a 3 by 3 kernel seem to function well
