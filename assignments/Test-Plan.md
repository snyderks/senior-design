# Test Plan

[< Back](/README.md)

[See testing results here.](/assignments/Testing-Results.md)

## Overall Test Plan

Given this is a research project, typical testing presents a challenge due to the more flexible requirements involved. However, much of the scaffolding and supporting infrastructure around the model *can* be tested and is the primary focus of the test. A second phase involves testing the ability to train, save, and then load a model so it can be reused instead of having to train a new model each time. The final test is to take a given lift, load the model, classify the lift, and output the resulting classification. 

## Test Case Descriptions

1. Normalization Test
    1. This test is designed to determine whether the normalization procedure on the data will proceed identically to an ingested lift.
    2. This test will randomly select a given lift from the training data, send it through the normalization process, and compare it to the output from normalizing all of the training data together. 
    3. The inputs are the list of training data and one element of those, randomly selected.
    4. The output is the normalized lifts; the randomly selected lift should be identical in each case.
    5. Normal
    6. Whitebox
    7. Functional
    8. Unit
2. Padding Test
    1. This test is designed to determine whether the padding procedure can recover from a minimal-size lift.
    2. This test will take a zero-length lift, send it through the padding and reshaping process, and determine whether it exits correctly with the correct dimensions.
    3. The input is a zero-length lift (a list of 18 empty lists).
    4. The output should be a `95x95x3` matrix consisting entirely of zeroes.
    5. Boundary
    6. Blackbox
    7. Functional
    8. Unit
3. Reshaping Test
    1. This test is designed to determine whether the reshaping procedure correctly maps input values to their corresponding output spaces.
    2. This test will take a manually defined lift, send it through the reshaper, and make sure that all values are mapped to their correct positions.
    3. The input is an ascending list of integers in a lift (a list of 18 lists, all with unique values)
    4. The output should be a `95x95x3` matrix with all unique values, with consecutive rows representing different sensors, columns representing different points in time, and layers representing different axes.
    5. Normal
    6. Blackbox
    7. Functional
    8. Unit
4. Ingestion Resiliency Test 1
    1. This test is designed to determine whether the system correctly recovers from a lift being passed that does not contain all the required sensor data.
    2. This test will take one of the original training set's lifts that is missing random columns (sublists) and pass it through the ingestion process to see if it crashes or correctly recovers.
    3. The input is one of the dataset's lifts with random columns removed.
    4. The output should be an error stating that the input could not be processed due to missing columns.
    5. Abnormal
    6. Blackbox
    7. Functional
    8. Integration
5. Ingestion Resiliency Test 2
    1. This test is designed to determine whether the system correctly ingests a lift being passed that does not have an equal amount of data points in all columns.
    2. The test will take one of the training set's lifts that has several of the data points in random columns missing and pass it through the ingestion process to make sure it successfully processes it.
    3. The input is one of the training set's lifts that has several of the data points in random columns missing.
    4. The output should be a `95x95x3` matrix with all given values present and padding for all other values.
    5. Abnormal
    6. Blackbox
    7. Functional
    8. Integration
6. Ingestion Resiliency Test 3
    1. This test is designed to determine whether the system correctly rejects a lift being passed that exceeds the maximum length the model supports.
    2. The test will take in a handcrafted example lift that exceeds the maximum size of `95x95x3` and check for a crash, a successful ingestion, or a returned error.
    3. The input is a lift that is too long for the system.
    4. The expected output is an error saying the lift is too long to analyze.
    5. Abnormal
    6. Whitebox
    7. Functional
    8. Unit
7. Ingestion Resiliency Test 4
    1. This test is designed to determine whether the system is correctly agnostic about the order of the columns in the lift sent to the system.
    2. The test will take in an example lift that has the columns randomly shuffled (but not to the original order) and check for successful ingestion and classification.
    3. The input is a shuffled example lift from the testing batch.
    4. The output is the classification of the lift, which should match it when not shuffled.
    5. Abnormal
    6. Blackbox
    7. Functional
    8. Integration
8. Model Encoding Test
    1. This test is designed to determine whether the model encoding/decoding process correctly saves the weights, layer configuration, and parameters and loads the model into memory accurately.
    2. The test will take a trained model, encode it, save it to disk, retrieve and decode that model, and then classify all testing data.
    3. The input is the trained model and the testing data.
    4. The output is two lists of classified outputs: the trained model's classifications of the testing set before and after the encoding/decoding process.
    5. Normal
    6. Whitebox
    7. Functional
    8. Integration
9. Classification Benchmark
    1. This test is designed to determine whether the classification process can be performed quickly enough to be run in near-real-time.
    2. The test will take a list of lifts and, for each one, preprocess it, shape it for ingestion, and classify it. The test will be run across the entire set of lifts and the time needed will be averaged.
    3. The input is the entire dataset.
    4. The output is the average time to preprocess and classify each lift, which should take less time than is necessary to generate another.
    5. Normal
    6. Blackbox
    7. Performance
    8. Integration

## Test Case Matrix

| | Normal/Abnormal | Blackbox/Whitebox | Functional/Performance | Unit/Integration |
|-|-----------------|-------------------|------------------------|------------------|
| NT | Normal | Whitebox | Functional | Unit |
| PT | Boundary | Blackbox | Functional | Unit |
| RT | Normal | Blackbox | Functional | Unit |
| IRT1 | Abnormal | Blackbox | Functional | Integration |
| IRT2 | Abnormal | Blackbox | Functional | Integration |
| IRT3 | Abnormal | Whitebox | Functional | Unit |
| IRT4 | Abnormal | Whitebox | Functional | Integration |
| MET | Normal | Whitebox | Functional | Integration |
| CB | Normal | Blackbox | Performance | Integration |