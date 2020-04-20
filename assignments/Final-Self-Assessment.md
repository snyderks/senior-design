[< Back](../README.md)

# Final Self Assessment

Kristian Snyder

## Part A

*What was your individual contribution to this project? Did you apply and build upon the skills identified in your initial assessment from last Fall? What did you do and how did you do it? What did you learn and what competencies did you build? What were your successes, what were you obstacles?*

As I was the sole member of my group, I contributed to all portions of the project. However, as it is a project extending from an existing research effort, I had the benefit of other members of my larger research group providing ideas to improve the model design, performance, and data analysis. I cannot take full credit for the project, then. Initial skills such as my experience with Python, data processing, and simplistic machine learning models were helpful. I advanced far beyond these initial skills. I now understand the internals of a convolutional neural network, interpreting accelerometer and gyroscope data, and signal processing due to this work.

I was able to build a machine learning model that acts as both a manual lifting classifier and detector, able to determine if a person is lifting something and whether their technique is likely to hurt them. The model itself is trained and tested off of data generously provided by the National Institute for Occupational Safety and Health. It is carefully annotated and well-collected, making it very useful for classification. I built the model itself with Keras on TensorFlow in Python, providing myself with experience in all of these technologies. My success, of course, was the success of the model, with over 90% accuracy as both a classifier and detector. Many previous models completely failed, however. This was a significant issue with model development, as tuned performance can vary up to 10 percentage points but still be unacceptable. Beyond simply setting up the data pipeline, these local maxima provided the most problematic setback.

## Part B

*What did your group accomplish? What did you learn about group work? What aspects of teamwork were successful and what aspects of teamwork were not successful? How did your efforts on the project compare to that of your teammates?  Do any team members deserve special recognition?*

As I was the sole member of my group, all things above were accomplished by the group. However, just because I was the sole member of the group didn't mean I worked in isolation. My advisor and other members of the research group provided insights into the model's development and data processing that were keys to success. I learned that group work can take many different forms. Even though I was working alone, I was still able to draw on the experiences and insights of my peers to be successful.

Overall, working on a project alone had both benefits and drawbacks compared to working in a group. I was able to plan much further in advance knowing my own working speed and ability. Several portions of the project, however, could have been completed in parallel. This was where I felt the issue of working alone most keenly; successful planning can result in more than enough work for multiple people to complete and finish the project more quickly.
