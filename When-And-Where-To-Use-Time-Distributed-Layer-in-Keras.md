# **Purpose of TimeDistributed:**
TimeDistributed applies the same layer(s) to each time step or element in a sequence individually. It’s usually used when you have sequential data (like videos, time-series, or sentences), and you want to process each element in the sequence the same way.

# **When to Use TimeDistributed:**
**At the Start of a Model (Before LSTM):**

If you need to process each item in the sequence independently before feeding the sequence to a recurrent layer like LSTM.
Example: You have a video (sequence of frames). You apply TimeDistributed(Conv2D) to each frame to extract features, then pass the features to an LSTM to capture temporal patterns.


**At the End of a Model (After LSTM):**

If your LSTM or recurrent layer is producing a sequence of outputs, and you want to apply the same layer to each of those outputs.
Example: After LSTM processes a sequence, you might apply TimeDistributed(Dense) to predict something for each time step.


**Example Scenarios:**

**Video Data (Frames as Input):**

Use TimeDistributed(Conv2D) at the beginning to apply convolution to each frame.
Pass the sequence of processed frames to an LSTM to capture temporal dependencies.

**Sequential Classification (Text, Time Series):**

If you want to apply a Dense layer to each time step after processing with LSTM, you can use TimeDistributed(Dense) after the LSTM.
