[WalnutiQ](http://walnutiq.com)
==========

“*Unless someone like you cares a whole awful lot, nothing is going to get better. It's not.*” ~ Dr. Seuss

[![Build Status](https://travis-ci.org/quinnliu/WalnutiQ.png)](https://travis-ci.org/quinnliu/WalnutiQ)

Welcome! WalnutiQ is a human brain model simulation in Java. 
The goal of this repository is to store code that can 
simulate a human brain in real-time. A brain machine 
without emotions which is more intelligent than the smartest humans 
will potentially be able to solve many of the problems which currently plague the world. 
If you are interested in becoming a researcher/developer, the only requirement is passion 
for applying brain models to solve real world problems.
 
Here you will find code that allows you to build a partial 
human brain model, train it on input data, view its activity 
as text and visual output, and test its ability to recognize 
objects. All of the code here supports modeling of the human 
brain at a high level of abstraction while still allowing user
access to individual neuron properties. For more information please 
watch this [video playlist](http://www.youtube.com/playlist?list=PLPXsMt57rLtgddN0NQEmXP-FbF6wt2O-f) 
to become familiar with the neuroscience behind this repository.

Most importantly, this research is made possible by the intelligent
neuroscientists and engineers at the company [Numenta](http://numenta.org/). 
Numenta has designed a exciting new technology that accurately models 
layers 3 & 4 of the human neocortex. They have generously released 
the pseudocode for their learning algorithms, and this repository is an 
extended implementation of their algorithms using object-oriented 
programming. Make sure to read Numenta's great explanation 
of their research in this [white paper](https://db.tt/FuQWQuwE) 
to better understand the theory behind this repository.

<h2>Setup in Linux/Mac/Windows with Eclipse</h2>
1. [Install Eclipse](http://wiki.eclipse.org/Eclipse/Installation)

2. Fork this repository and clone it locally. Then import it as a 
project into Eclipse.

3. IMPORTANT: You will notice that your folders will have "red X's". To fix this right 
click your ```src``` folder then hover over "New", then click "Source Folder". 
Then give it the "Folder name:" src. You will also need to do this same process for the folders 
```tests```, ```images```, and ```train```. Make sure when you type the "Folder name:"
you put in the folder name of the folder you previously just right clicked.

4. In Eclipse, add all the libraries (.jar file) in the folder 
```referencedLibraries/``` by right-clicking your project in the package explorer 
=> Build Path => Add External Archives...

5. In Eclipse, also add JUnit 4 & jre7 to your build path. Then 
right click the ```WalnutiQ/``` folder and select "Run As" => 
"JUnit Test". Make sure all tests pass!
  
<h2>Setup in Linux/Mac/Windows with Gradle</h2>
1. Install Gradle in Linux OR Mac by typing to the command line:
```
linux> wget http://services.gradle.org/distributions/gradle-1.10-bin.zip
linux> sudo unzip -q gradle-1.10-bin.zip -d /usr/local/
linux> echo "export GRADLE_HOME=/usr/local/gradle-1.10" >> .profile
linux> echo "export PATH=$PATH:$GRADLE_HOME/bin" >> .profile
```

2. Or install Gradle with these [instructions for Windows](https://db.tt/DMF3ww2D)

3. Fork this repo and clone it locally. Navigate into the ```WalnutiQ/``` folder

4. Type in the command line ```gradle build```. This may take a minute so no worries.
Go to the folder ```build/reports/tests/```. View the file ```index.html``` in 
a browser and make sure all tests pass!

<h2>How to Contribute</h2>

1. View an example of how all the code is used in the file: 
```
WalnutiQ/train/model/MARK_I/HowToUseMARK_I.java
```

2. View the [TODO List](./TODOList.md) and find a task you 
would like to work on or suggest a new task if you kind of know what you
are doing. Happy coding!

<h2>What each file/folder in this repository is for:</h2>
  - images
      + digits
          - [MNIST](./images/digits/MNIST) = unique files that contain training images and testing images
      + model = images used in testing the MARK I model
  - referencedLibraries = contains .jar files needed to run the program
  - src
      + model
          - [MARK_I](./src/model/MARK_I) = the core logic for the partial brain model. Includes abstract data types
          	for basic brain structures and learning algorithms that simulate how 
          	the brain learns
            + [connectTypes](./src/model/MARK_I/connectTypes) = classes allow the different brain structures in MARK I to 
              connect to each other in a variety of ways
          - [theory](./src/model/theory) = contains a class MemoryClassifier.java for identifying what
            category a new image is in given a nervous system that has been trained on images from this category (Currently not working)
          - [util](./src/model/util) = classes that enable the brain model properties to be viewed
            graphically and efficiently saved and opened
  - tests = test classes for important classes in the ```src/``` folder
      + model
          - [MARK_I](./tests/model/MARK_I)
            + [connectTypes](./tests/model/MARK_I/connectTypes)
          - [theory](./tests/model/theory)
          - [util](./tests/model/util)
  - train  
      + model
          - [MARK_I](./train/model/MARK_I) = demonstrations of how to build and train a partial brain model
                     on a popular handwritten digit data set called MNIST
  - .gitignore = contains names of files/folders not to add to this repository
  - .project = when writing your code using Eclipse this file will allow all of
               your files to be organized in the correct folder
  - .travis.yml = tells [our custom travis testing site](https://travis-ci.org/quinnliu/WalnutiQ) 
    how to test the files here
  - BrainTheories.md = list of brain theories with support and simple explanation
  - README.md = the file you are reading right now
  - TODOList.md = list of research & programming tasks to do
  - build.gradle = Groovy language code for compiling all of the code in this repository using Gradle

===============================================================
Please contact me at quinnliu@vt.edu if you have any questions! 