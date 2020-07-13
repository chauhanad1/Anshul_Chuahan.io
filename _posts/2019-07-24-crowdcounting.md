---
title: " A project for crowd disaster management"
date: 2019-07-24
tags: [Machine Learning]
header:
    image: "/images/crowdcounting/main_pic.png"
excerpt: "Machine Learning, RCNN, Transfer Learning"
---

 

 > **It is a project to manage crowd disasters which are very common in a country like India where population density is very high. Any crowd disaster can take many life in such places. So, it is very important to keep a check in the number of people in a public area so that crowd can be managed. Here comes our project to the rescue. It identifies and counts the number of persons in the area which can generate a trigger alarm if the number reaches more than a threshold value.**

 Here is a [link](https://github.com/chauhanad1) to the code of the project

 **The Project proceeds as follows:**
 1. *Preparing Dataset*
    1. Collect as many pictures as possible of the people in crowd.
 2. *Labelling the Dataset*
    1. Use a labelling software to label the images.
    2. I used *labelImg* to annotate the dataset in pascal format.
    3. This will generate .xml file for every image.
 3. *Generating records for training*
    1. To use less processing time we again converted the .xml file to .csv
    2. The code for conversion is:

     ```python
    def main():
        for folder in ['train', 'test']:
            image_path = os.path.join(os.getcwd(), ('images/' + folder))
            xml_df = xml_to_csv(image_path)
            xml_df.to_csv(('images/'+folder+'_labels.csv'), index=None)
            print('Successfully converted xml to csv.')
    ```
       Then the csv files are converted to TFrecords as below:

    ```python
    def class_text_to_int(row label):
        if row_label == 'person':
            return 1
        else:
            None
     ```
 4. *Configuring Training*
    1. In this step a labelmap is created whose number is same as the TFrecord file.
    2. faster_rcnn_inception_v2_coco model is used in the project and few tweaks are done in the config file to suit   our needs in the project.
 5. *Training Model*
    1. Since it is a transfer learning algorithm, we used the train file to train our dataset on crowds.
 6. *Exporting Inference Graph*
    1. Inference graph is generated using highest step number file that is finding the biggest index number in model.ckpt


The Output of the project looks like:
<img src="{{ site.url }}{{ site.baseurl }}/images/crowdcounting/crowd_new.png" alt="Test result">