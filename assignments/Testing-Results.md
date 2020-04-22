# Testing Results

[< Back](/README.md)

## Normalization Test

*This test is designed to determine whether the normalization procedure on the data will proceed identically to an ingested lift.*

Normalization test has passed successfully *when the normalizer has been stored externally and loaded prior to normalization.* This implies a need for a normalizer to be included in a real-world situation for consistency.

## Padding Test

*This test is designed to determine whether the padding procedure can recover from a minimal-size lift.*

Padding test passed successfully with a completely empty trial labeled with class `NONE` - it entered the pipeline without any issues. Note that the headers of the trial were still present. The data, however, did not exist.

## Reshaping Test

*This test is designed to determine whether the reshaping procedure correctly maps input values to their corresponding output spaces.*

The reshaping test passed successfully on a variety of data structures - it was tested by removing sensor data from the pipeline and still produced the most compact possible square for the data's maximum size. In the case of all the sensors, it produced a `95x95x3` matrix as expected.

## Ingestion Resiliency Test 1

*This test is designed to determine whether the system correctly recovers from a lift being passed that does not contain all the required sensor data.*

This test was discarded for its lack of relevance at the layer developed. Data validation happening directly at the model level was deemed to be irrelevant and should happen earlier up the chain by detecting if a sensor is not reporting data.

## Ingestion Resiliency Test 2

*This test is designed to determine whether the system correctly ingests a lift being passed that does not have an equal amount of data points in all columns.*

Testing this feature worked on the first try; the `DataFrame` type automatically pads ingested data with zeroes in any column not meeting the minimum.

## Ingestion Resiliency Test 3

*This test is designed to determine whether the system correctly rejects a lift being passed that exceeds the maximum length the model supports.*

At the model level, this will crash still. A handler was added to the testing phase that truncates any path longer than the maximum size (without padding) and allows it to safely enter the model.

## Ingestion Resiliency Test 4

*This test is designed to determine whether the system is correctly agnostic about the order of the columns in the lift sent to the system.*

The lookup system for `DataFrame` allows for out-of-order column indexing and so the columns can be in any order and were tested as such.

## Model Encoding Test

*This test is designed to determine whether the model encoding/decoding process correctly saves the weights, layer configuration, and parameters and loads the model into memory accurately.*

Saving the model is, luckily, simple enough as Keras supports [model saving natively.](https://keras.io/getting-started/faq/#savingloading-whole-models-architecture-weights-optimizer-state) Therefore, this test was only run once and is no longer necessary since no additional code had to be written to support it.

## Classification Benchmark

*This test is designed to determine whether the classification process can be performed quickly enough to be run in near-real-time.*

Running classification on all testing samples (180 for the initial model configuration) took an average of 4 seconds. Given a sample lift window of 5 seconds, this should be able to perform more than satisfactorily on low-power hardware.