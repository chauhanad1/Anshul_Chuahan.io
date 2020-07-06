---
title: " A project for crowd disaster management"
date: 2019-07-24
tags: [machine learning, RCNN, Transfer Learning]
header:
    image: "/images/crowdcounting/img1.jpg"
excerpt: "Machine Learning"
---

 # Crowd Counting project

 > It is a project to manage crowd disasters which are very common in a country like India where population density is very high. Any crowd disaster can take many life in such places. So, it is very important to keep a check in the number of people in a public area so that crowd can be managed. Here comes our project to the rescue. It identifies and counts the number of persons in the area which can generate a trigger alarm if the number reaches more than a threshold value.

 Here is a [link](https://github.com/chauhanad1) to the code of the project

 This is how the porject proceeds
 1. Preparing Dataset.
 2. Labelling the Dataset.
 3. Generating records for training.
 4. Configuring Training.
 5. Training Model.
 6. Exporting Inference Graph.

 Here's the code to convert dataset from xml to csv:
 ```python
    def main():
        for folder in ['train', 'test']:
            image_path = os.path.join(os.getcwd(), ('images/' + folder))
            xml_df = xml_to_csv(image_path)
            xml_df.to_csv(('images/'+folder+'_labels.csv'), index=None)
            print('Successfully converted xml to csv.')

 ```

This is how to generate TFrecords:
```python
    def class_text_to_int(row label):
        if row_label == 'person':
            return 1
        else:
            None

```

This is the result:
<img src="{{ site.url }}{{ site.baseurl }}/images/crowdcounting/testf.png" alt="Test result">