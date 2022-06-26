## Week 1 & 2
### Working on Hard-Cut detector

In these two weeks, I primarily worked on the previously worked on the previosuly developed Hard-Cut Detector module of the FilmEditDetection tool. Primarily three additions were made to the module : 

- A system to plug and play any CNN model of choice in the hard-cut detector module using a network configuration file.
- Option to parallely process different parts of the film in different CPU cores.
- A progress bar which shows the extent of computation completed.

#### A system to plug and play any CNN model of choice

In the previous version of the tool, only a fixed CNN could be used in the hard-cut detection module. I have added an option to change the CNN according to user's choice through a network configuration file, which is a JSON format file. Informations about the hard-cut network like `CNN`, `threshold`, `Input_Shape`, etc. can be explicitly defined through this file. The config file is usually stored at the `\configs\`.

This actually helped me in trying out different CNN networks, and thresholds to compute the results, and set an optimal network and threhsold for the hard-cut detectioon module.

#### Parallely process different parts of the film in different CPU cores.

Each operation in hard-cut detection module is computationally expensive. Hence, it is a good idea to parallelize the entire process. I approached the problem by spliiting the films into several parts and computing each parts seperately in seperate CPU cores. Python package `multiporcessing` has been used to parallelize the process.

It has been observed that there is a reduction of 20% computational time by parallelizing the process from 1 core to six core. The number of core to be used can also be explicitly defined in the `config.json` file under the key `child_process`.

#### A progress bar

As the entire process is heavily time-consuming, a progress bra which would help in keeping track of the entire process, like the percentage completed, estimated time left would be really handy. The discussed functionality has been added to the tool using the python library `tqdm`.




Upon testing a wide variety of films, with a number of CNN models in the hard cut detection module, I found that ResNet50 and VGG16 are the CNNs which performed way better than the rest in terms of computational time and performance. ResNet50 with a threshold of 0.75 and VGG16 with a threshold of 0.85 can be the go-to networks for the hard-cut detection module. The network config file are preovided in the repository. ResNet50 is slightly more accurate than VGG16, but VGG16 does computation faster about 10% than ResNet50. It is confirmed that these networks can handle the 'over-exposed' film which were an issue to the previous version of the tool. 

I have also updated the documentation about the usage of the tool.

