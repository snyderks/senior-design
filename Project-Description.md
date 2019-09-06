# Predicting Back Injury Risk for Workers

## Team Members

Kristian Snyder (snyderks@mail.uc.edu)

## Faculty Advisor

Dr. Rashmi Jha (jhari@ucmail.uc.edu)

## Project Background

Back pain is an extremely common ailment, with 23.2% of the world’s population
affected in any given month. While there are many causes, lifting in poor
posture is one of the main risk factors for back pain. Low back pain is the
largest contributor to the total workers’ compensation cost. The total health
care expenditures incurred by individuals with low back pain alone in the United
States reached $90.7 billion a year. Improvements or solutions to this workplace
health issue would not only reduce incidences of injury and lower workers’
compensation expenses, but also increase work productivity.  Additionally,
workers with healthy backs would have longer careers and improved well-being.

While the causes for back pain are relatively well-known, previous solutions
have been limited to training, physical therapy, and other methods that only
work either before or long after the events causing pain. This prevents
internalization and instinctual recognition of the problem in the most important
situations: where it occurs.

## Problem Statement

How can we give workers near-immediate recognition that the way they are lifting
objects will increase their risk of back pain?

## Lacking Solutions

While some prototyped solutions seeking to solve this problem exist, they have
several impracticalities:

- High cost from a high number of sensors
- Encumbering design due to an exoskeleton to support the overall structure
- Difficult to take on, off
- Some customization to each individual worker may be required

Consequently, there is a reticence to adopt these technologies because their
cost is far in excess of potential benefits to worker productivity and
disability benefits. Additionally, the ergonomic drawbacks of existing solutions
make them unpopular among workers, further hindering their adoption.

## Applicable Background

Skills:

- Various coursework (AI, Intelligent Data Analysis, Python Programming)
- Previous research work in Python
- Data processing experience from co-op positions

Interests:

- Machine learning model development
- Data cleanup, processing, analysis
- Python

## Approach

Overall goal: a high-accuracy model that can recognize high, medium, and
low-risk lifting of objects.

The data source will be from 6 total sensor clusters placed along various parts
of the body (waist, arm, wrists, back, thigh) and will consist of a gyroscope
and accelerometer at each location. Data are sourced from an existing study
driven by NIOSH to study behavior during lifting and will run in parallel.

Auxiliary goals (not a primary goal for existing research but driving toward the
purpose):

- The ability for the model to work on-line and recognize unsafe lifts in
  near-real time
- A live demo with the sensor cluster showing the classification
- More granular recognition of where, relative to the person, where they were
  lifting the object from

Generally, the process will involve three major steps in developing the model:

- Importing and splicing the data to structure it for training
- Applying various preprocessing steps to reduce noise, highlight potential
  features, and normalize the data for import into a machine learning model
- Selection, tuning, and training of the model to best classify the pre-labelled
  data

Additional steps, if the primary goal is completed, will of course be necessary.
