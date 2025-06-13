# ⁉️  What is CIFAR-10
CIFAR-10 is a dataset that contains images from 10 classes: ('airplane', 'automobile', 'bird', 'cat', 'deer', 'dog', 'frog', 'horse', 'ship', 'truck').
It consists of 60,000 color images, each of size 32x32 pixels in RGB format.

The dataset is split into:

50,000 training images (used to train the model)

10,000 testing images (used to evaluate the model's performance)

You can import the CIFAR-10 dataset either by downloading it manually or by using TensorFlow’s built-in dataset loader — as used in this repo.

# cell 1️⃣

<img width="376" alt="Screenshot 2025-06-13 at 15 06 34" src="https://github.com/user-attachments/assets/42ff7db5-0134-4e72-a612-74135aabbd41" />

Used Keras, which is a high-level API built on top of TensorFlow. Imported pyplot from matplotlib to visualize the model’s performance (optional, but helpful).

# Cell 2️⃣ 

<img width="664" alt="Screenshot 2025-06-13 at 15 10 26" src="https://github.com/user-attachments/assets/47f6c8fe-6658-4cd9-8ea7-469d6e25fcc8" />

* x_train: The training images (50,000) → Input

* y_train: The labels for x_train → Output

* x_test: The testing images (10,000) → Input

* y_test: The labels for x_test → Output


The function tf.keras.datasets.cifar10.load_data() downloads and loads the dataset for you.

<img width="378" alt="Screenshot 2025-06-13 at 15 30 25" src="https://github.com/user-attachments/assets/914e8074-4fc4-465f-8d8a-25193b8b608e" />

We normalize the input values to be between 0 and 1. This helps the Neural Network process smaller, more manageable values instead of full pixel values from 0–255 (which is the range of 8-bit color channels).

*Why is this important?

*Using big numbers slows down training

*It can also make the model unstable due to large gradients

*Normalization helps the model converge faster by keeping values in a tighter range

<img width="829" alt="Screenshot 2025-06-13 at 15 38 05" src="https://github.com/user-attachments/assets/e1643d79-9dbb-49a4-90ea-6f17ca83df05" />

*batch_size: Splits the dataset into smaller groups (64 examples per batch). Helps the model train more efficiently.

*cache: Keeps the dataset in memory for faster access during training.

*shuffle: Randomizes the dataset to prevent the model from memorizing the order.

*prefetch: Loads the next batch in the background while the model is training.

*AUTOTUNE: Automatically chooses the best prefetch buffer size based on system resources (CPU, GPU, memory, etc.).

# cell 3️⃣
<img width="634" alt="Screenshot 2025-06-13 at 15 47 21" src="https://github.com/user-attachments/assets/d2525275-6772-43da-837d-cbe2bfa5727e" />

*This is a basic Convolutional Neural Network (CNN) setup

*You can modify any part of the architecture except the final Dense layer, which must be 10 because we have 10 classes

*Dropout: Randomly disables a percentage of neurons during training to prevent overfitting and improve generalization

*optimizer='adam': Popular optimizer that adjusts weights efficiently

*loss: We're using SparseCategoricalCrossentropy because labels are integers (not one-hot encoded)

*from_logits=True: Tells the loss function that the model’s output hasn’t passed through a softmax yet

*metrics=['accuracy']: To monitor accuracy during training

# cell 4️⃣
<img width="297" alt="Screenshot 2025-06-13 at 15 51 07" src="https://github.com/user-attachments/assets/99b9d54a-4650-4392-aace-5a596ef151ac" />

This is where the model starts learning!

*I used 15 epochs here — you can change that to whatever you want

*epochs = number of full passes the model takes over the dataset (like "laps" in a race)

<img width="556" alt="Screenshot 2025-06-13 at 15 52 42" src="https://github.com/user-attachments/assets/681295c0-144b-406d-9ab9-7e71b9d9ee7f" />

This part is just for visualization



 



