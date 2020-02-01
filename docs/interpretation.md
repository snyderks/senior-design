# Interpretation

This page describes how to interpret the results of the model training.

## Heatmap

The heatmap displays the confusion matrix of the testing results. If you don't
know what a confusion matrix is, see [this page](https://en.wikipedia.org/wiki/Confusion_matrix).

Specifically, concentrate on the row-normalized version of the heatmap for the
best interpretation. The row-normalized version corrects for different class
sizes (they are not equal) and so is a more accurate depiction.

## Swarm Plot

The swarm plot displays the distribution of the predictions for each class
tested. The x-axis is the true class labels. The y-axis is the scalar-converted
predicted label (for 1 = low, 2 = med, 3 = high), determined by taking the
confidence in each label and multiplying that by the label to get the total
amount.
