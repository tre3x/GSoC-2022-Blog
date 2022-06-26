## Google Summer of Code 2022

I am excited to be a part of Google Summer of Code 2022, working with Red Hen Lab on the project 'Machine Detection of Film Edits'.

The project aims at developing a tool which is able to detect and classify cuts in archive films, which are really hard to detect by already available tools  due to various 
factors like - noise, broken frames, low constrast change between two shots. The development of the project started last year, and a preliminary tool able to solve the problems discussed. This year, the tool will be getting a revamp - ranging from a improving the efficieny of the tool to developing a possible UI of the tool.

The abstract of the work to be done this year is stated below:

Shot Boundary Detection of films is an important task that is mostly performed manually. There are some available tools and existing research which tend to automate the process. However, in the case of old archival films, available tools fail to detect most of the shot boundaries. State-of-the-art research performs quite well in detecting these boundaries, but these methods come with high time complexity and are not feasible to use in real life. In this work, an efficient and accurate shot boundary detection is proposed which should work well with archival films. The proposed tool will be built upon the existing work 'FilmEditDetection', which is developed during the last summer of code. The proposed tool should be able to detect the shot boundaries, which the previous tool fails to detect, without compromising the time complexity of the entire tool. This is achieved by using a machine learning-based framework on top of the cut detection module(Siamese Network). Few new features are also to be added to the tool - Average Shot Length, Comparison of individual shot lengths, etc. The current version of the tool is based on CLI. A graphical user interface can be developed based on the tool for simplicity of use.


### [Week 1 & 2 : Working on Hard-Cut detector][https://tre3x.github.io/week1]

In these two weeks, I worked on the previosuly developed Hard-Cut Detector module of the FilmEditDetection tool. Primarily three additions were made to the module : 

- A system to plug and play any CNN model of choice in the hard-cut detector module using a network configuration file.
- Option to parallely process different parts of the film in different CPU cores.
- A progress bar which shows the extent of computation completed.