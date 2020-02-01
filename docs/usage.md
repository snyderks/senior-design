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
current cell and move to the next, SHIFT+ENTER). The 6th cell should output the
number
of samples (683) and the number in the test and train subsets (512 and 171).

## Training

To train the model, run the 8th cell. This will begin the training process and
should take about 10 minutes. Depending on the parameters (edit `one_params`),
the model may not converge, in which case it will halt after 300 epochs.

The final output is a confusion matrix of the testing results. See [here for an
explanation of a confusion
matrix](https://en.wikipedia.org/wiki/Confusion_matrix).

## Saving Model

Model saving is currently under development and not supported yet.

## Output Plots

To generate output plots, run the next cell (cell 9) `trial_plots` function to
create a heatmap and swarm plot of the results.

![Example heatmap](./heatmap-example.png)
![Example swarmplot](./swarm-example.png)


