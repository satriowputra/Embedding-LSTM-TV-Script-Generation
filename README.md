# Embedding-LSTM-TV-Script-Generation

## Overview
Here i am using Embedding-LSTM to generate TV script based on Seinfeld Dataset.

## File Description
There are several files i upload here:
1. workspace_utils.py: contains function to prevent workspace being disconnected while running long processes.
2. helper.py: contains function to preprocess data, save and load our model.
3. problem_unittest: testing functions for created function.
4. preprocess.p: processed dataset.
5. generated_script_1.txt: contains generated text resulted from our model.

## Result
- *sequence length:*<br>
The larger value is usually the better result from out network. This required longer computational time, but in return the network can learn longer dependencies from our text and give us better prediction.<br>
- *hidden and embedding dimension*<br>
These parameters are also affecting computational time, the higher the longer it takes to finish the training with 10 epochs. Fortunately, by increasing these values our error is decreasing.

I have tried several hyperparameters configuration for our network to make sure what is the effect to our final loss. Here are the results:

| No. | sequence_length | batch_size | num_epochs | learning_rate | embedding_dim | hidden_dim | n_layer | Loss |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | 10 | 32 | 10 | 0.005 | 100 | 100 | 3 | 4.63622 |
| 2 | 10 | 64 | 10 | 0.005 | 150 | 150 | 2 | 4.12622 |
| 3 | 20 | 128 | 10 | 0.001 | 200 | 200 | 2 | 3.27783 |
| 4 | 10 | 128 | 10 | 0.001 | 200 | 250 | 2 | 3.19439 |
| 5 | 20 | 128 | 10 | 0.001 | 250 | 250 | 2 | 3.18688 |
| 6 | 20 | 128 | 10 | 0.001 | 300 | 300 | 2 | 3.09776 |

The best result is last configuration above. This give us loss of 3.09776.

Please find the generated text from our model in `generated_script_1.txt`
