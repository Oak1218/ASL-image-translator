# ASL-image-translator
This is an AI that has been trained with images of six American Sign Language letters, A, E, O, R, S, and T. The AI uses DetectNet to identify
which letter you are showing based on the dataset it has been given.

![r_hand1](https://github.com/user-attachments/assets/65bc4c85-c36d-46c8-bbf5-6b65a796b032)

![ohand](https://github.com/user-attachments/assets/92da30a7-dfa4-436d-8b91-0a9152552238)

## The Algorithm
The algorith for this AI uses the Nvidia Jetson Nano and the Google's trained AI image recognition to identify what letter you are showing in American Sign Language.
Once you have connected your Jetson Nano and opened VS code you can upload your dataset to VS code. After running the code to train your model using ImageNet. After training the AI you export it to the using Resnet-18 so that it can be used with a seperate image and test what letter it is. This specific model can only be used to identify the letters A, E, O, R, S, T.


## Running this project

1. Set up Jetson Nano and install VS code.
2. Connect Jetson Nano onto your computer hotspot.
3. Connect VScode to your Jetson Nano using conenct host and ssh nvidia@IPAddress
4. Open the Nvidia home folder.
5. Open the terminal and use cd jetson-inference/python/training/classification
6. Make sure your dataset is in the data folder and split 80% in training, 10% in validation, and 10% in Test.
7. Create a file called labels.txt and write the names of your different catagories identical to how they appear in the test, train, and val folders.
8. Use NET=models/asl_dataset and DATASET=data/asl_dataset to set Net and Dataset for the next command\
9. Pick which letter you want to analyse and copy the link of the image.
10. Run the command 'imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/[name of classification]/[image link] [Output name]'
11. Find the image with the same output name you typed and see what it is classified as.

[View a video explanation here](video link)
