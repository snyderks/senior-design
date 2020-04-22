# User Interface

[< Back](/README.md)

As Lupe is designed to be inserted into a sensor cluster system and simply provide one result out, it does not have a typical user interface. However, a summary of the way the training and classification processes take place are in the [design diagrams](./assignments/Design-Diagrams.md) and briefly described below.

The reshaping process that allows a trial to be ingested into the system is under `xyz_reshaper()`, which takes a vector trial and, given a maximum length for all the trials, will determine the smallest possible 3D matrix with a depth of 3 and convert the trials into this format.

The root function for the processing itself is `prepare()`, which takes in a list of filenames and class names to ingest various CSVs containing the training and testing data. It outputs the aforementioned 3D matrices with a list of class names alongside them.

Training is performed with `trainer()`, which takes a dictionary of various model hyperparameters that can be tweaked to change the behavior of how aggressively the model pursues an accurate solution. This can vary from no restriction at all, typically resulting in overfitting, to heavy restriction on model complexity that will impact the performance of the model significantly.

Various functions, as shown in the documentation, exist to generate result plots such as heatmaps, swarm plots, and saliency maps. See the [documentation](/docs/README.md) for more information.