# Context

The goal of this project is to create a spam filter. We will utilize the computer and how it:

1. Learns how humans classify messages.
2. Uses that human knowledge to estimate probabilities for new messages — probabilities for spam and non-spam.
3. Classifies a new message based on these probability values — if the probability for spam is greater, then it classifies the message as spam. Otherwise, it classifies it as non-spam (if the two probability values are equal, then we may need a human to classify the message).

The dataset we will be using was put together by Tiago A. Almeida and José María Gómez Hidalgo, and it is named `SMSSpamCollection` in the files.

# Objective

We will be creating a function/ model to distingush spam or non-spam messages in new data with an accuracy of 80% or more.

# Process

- First, we split the dataset into 2 new datasets: `train` and `test`. This helped with testing our function/ model later for validation.
The `train` set held 80% of the original dataset and the `test` set held the remaining 20%.

- Then, we clean up the `train` data by removing unnecessary characters, lowering all characters, etc.

- Next, we tokenize each word in all the messages and added them as columns to the datasets. Each of these columns holds a `1` or a `0` to signify its presense in the original message.

- From this format, we calculate the probability of each word given its in a spam or non-spam message.
Then, we calculate the probability of messages being spam or non-spam given the words in them (and their probabilities calculated in the step above).
Note: we utilze Laplace's smoothing to avoid errors of 0% probability.

- Finally, we create a function, `classify` that uses the probabilities calculated above to classify new messages as spam or non-spam.

# Results

The function has a 94% accuracy on the `test` dataset and exceeds our initial 80% accuracy benchmark.
