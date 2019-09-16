# Back Injury Risk Individual Capstone Assessment

Kristian Snyder 9/15/19

## Introduction
 
Predicting and understanding the potential risk of back injury in workers is
about helping to mitigate risk and improve their lives. As this is also an
ongoing research project, my data originate from a previous study by the
National Institute for Occupational Safety and Health (NIOSH) seeking to
understand body motion when lifting objects. As stated in the project overview,
the primary goal is to understand the data sufficiently to build a predictive
model that can, with a high degree of accuracy, determine whether someone is
likely to hurt themselves when lifting an object. The definition of likely is
based on the NIOSH lifting zones diagram (shown below). Areas far away from the
body on a relative basis (3, 6, 9, 12, etc.) are considered to be more risky
than areas close to the body (4, 5). While the primary goal is to determine a
sufficiently accurate model for the data, an auxiliary goal is to eventually
convert this model to one that can preprocess on-line data and make
determinations in near real-time.

## College Experiences
 
Undoubtedly, the most critical courses for my possible success will be
Intelligent Data Analysis, Software Engineering, and Python Programming. As the
process centers on data analysis and machine learning, IDA (CS6052) has been
extremely helpful in understanding and developing the model. From better
understanding statistical rigorousness through folding and test-train splitting
to analyzing what types of data are compatible with different models (e.g. long
short-term memory networks, convolutional neural networks, support vector
machines), it has helped me avoid types of models that would have undoubtedly
been a lost cause. Software Engineering (EECE3093C), meanwhile, assists by
rounding out my understanding of software architecture, refactoring, and
planning updates to the processing and model. Without this course, I doubt I
could have understood how to build the various (and there are already many)
steps of ingesting, processing, and training on the data. Finally, Python
Programming (CS2021) helped to bypass learning the basic of Python, allowing me
to focus instead on understanding the various libraries required to build
models.

Both Great American Insurance and GE Aviation, through my various assignments,
provided me with the experience of working with complicated systems that are
impossible to fully hold in one's mind and require external structure to modify
safely. At Great American, my work in full stack software development would
frequently require modification of several layers of the application; enabling
rapid iteration required strong and consistent separation of these layers to
prevent interdependence that couldn't be untangled easily. Working within a
machine learning model, a significant portion of the work involves massaging the
data to fit the model's requirements and I have worked and will continue to work
on ensuring this stays modular and steps can be removed and added quickly. At GE
Aviation, my work in platform automation taught me that creating processes early
and systematizing repetition can save enormous amounts of time in the long run,
especially when individual iterations and changes can require significant
periods of compiling or, in my case, retraining the model. Therefore, knowing
when something won't work quickly through testing and failing fast has already
saved me numerous hours.

## Motivation and Approach
 
As this project is also a continuation of my undergraduate research and will
become my graduate thesis, I must state that this is my primary motivation to
improving the process and hopefully succeeding. However, the challenge of
recognizing unsafe lifting behavior is extremely important and I am glad that
some of my existing experience in software development and machine learning can
help in a space that typically focuses entirely on expertise in sensor creation
and ergonomic design. Having a consistently accurate model would enable
significant strides in this space. Existing solutions are extremely
human-intensive (physical therapy; in-depth, continuous training; in-person
monitoring) and so are not scalable to workers that either cannot be monitored
or trained sufficiently. I hope that I can succeed in developing this model
because it could be applied to provide these people with the feedback and
monitoring that they can use to make their bodies healthier not only during
their careers but also in later years, when the effects of dangerous behavior
are revealed to be debilitating.

Possible design paths for a solution will include a hot-swappable approach,
where I can objectively change steps in both the processing and training
process, running numerous simulations to rank them. While I have the general
idea that a convolutional neural network would perform best here, simply
choosing the model is hardly all I need to do and automating that selection
process is going to be critical. Luckily, my requirements for success are
simple: high accuracy and informedness (informedness referring to the likelihood
that the model is not simply guessing but making correct decisions based on what
it has recognized in the data). If I can achieve this, the next step will be
converting the pipeline to operate on on-line data and backing up the model so
it can be loaded easily. If I cannot achieve a high degree of accuracy (while I
hope to avoid this, it is extremely possible), understanding why it was not
possible is critical. This could be that existing models simply cannot extract
features from the data, that the data itself simply does not have enough
variation to be classified, or other justifications.