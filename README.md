# Traffic Sign Detection

Most of the current state of art solution to this well researched problem is using different types of deep learning based pipeline. Their choice of using model is based to priority difference given to computation time and accuracy. The faster one uses YOLO, SSD etc and model with better accuracy uses Feature pyramid network, Faster RCNN, Segnet etc. Here we propose a conventional approach of traffic sign detection i.e. using Traditional feature descriptor like SURF and HOG. The pipeline of our proposed algorithm is as following. First of all we propose Region Proposal folowed by calculating feature descriptor followed by a neural network. Each of the method is explained properly in sub-section. 
 

## Region Proposal

Firstly we tried a basic image processing based pipeline for traffic sign detection. Here in this, we know that traffic sign generally have red color so we take the red channel of the given image and apply threshold. We thresholded top 20% of total pixels. After this we used watershed algorithm as well as contour detection to propose region out of that.(The code for this is /segmentation/fianl_segmentation_ip.py). After this we tried to propose using Haar. We trained a Haar cascade classifier to propose ROI, the results for the same can seen /output/roi_haar. The method worked pretty well with a decent accuracy. The time taken by the haar Region of proposal is 0.1 seconds. We have also tried to implement the cascade classifier using cuda enabled opencv. The code for the same can be found at /GPU_implemetation/haar.cpp. The only boundation to implement this to have cuda enabled opencv in the machine.   

 ![alt text](https://github.com/harsh-99/Traffic-sign-detection/blob/new/Outputs/roi_haar/roiimg1.jpg)
 ![alt text](https://github.com/harsh-99/Traffic-sign-detection/blob/new/Outputs/roi_haar/roiimg4.jpg)
 ![alt text](https://github.com/harsh-99/Traffic-sign-detection/blob/new/Outputs/roi_haar/roiimg3.jpg)
### Feature descriptors

What things you need to install the software and how to install them

```
Give examples
```

### Neural Network

A step by step series of examples that tell you how to get a development env running

Say what the step will be

```
Give the example
```

And repeat

```
until finished
```

End with an example of getting some data out of the system or using it for a little demo

## Running the tests

Explain how to run the automated tests for this system

### Break down into end to end tests

Explain what these tests test and why

```
Give an example
```

### And coding style tests

Explain what these tests test and why

```
Give an example
```

## Deployment

Add additional notes about how to deploy this on a live system

## Built With

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - The web framework used
* [Maven](https://maven.apache.org/) - Dependency Management
* [ROME](https://rometools.github.io/rome/) - Used to generate RSS Feeds

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 

## Authors

* **Billie Thompson** - *Initial work* - [PurpleBooth](https://github.com/PurpleBooth)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone whose code was used
* Inspiration
* etc

