# Basic Usage

[Docs Home](/docs/README.md)

## Caveats

As this is still in progress, a CLI has not yet been developed and is still in
progress. All usage is through the Jupyter Notebook.

## Startup

From the root directory, run `jupyter notebook` from your terminal on Linux or
the Anaconda terminal on Windows.

A window should open in your default browser. Click on `Hi Dimension
(CURRENT).ipynb` to open the notebook.

Run the first 6 cells (to run the current cell, hit CTRL+ENTER; to run the
current cell and move to the next, SHIFT+ENTER). This will prepare the underlying model structure.

To set up the train test split for the first time, run the 7th cell. To save off the split, run the 8th cell. To load this split later, run the 9th cell.

## Training

To train the model, run the 11th cell and the 17th cell. This will begin the training process and
should take about 10 minutes. Depending on the parameters (edit `one_params`),
the model may not converge, in which case it will halt after 300 epochs.

The model will output the final validation accuracy and return the model itself and the confusion matrix of the results. The confusion matrix is printed after returning.

The final output is a confusion matrix of the testing results. See [here for an
explanation of a confusion
matrix](https://en.wikipedia.org/wiki/Confusion_matrix).

## Saving Model

Save the model with `model.save` in a new cell.

## Output Plots

To generate output plots, run cells 18-20 to
create a heatmap, swarm plot, and saliency map of the results.

![Example heatmap](./heatmap-example.png)
![Example swarmplot](./swarm-example.png)


