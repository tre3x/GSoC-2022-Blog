## Blog 5
### Added Graphical User Interface to the tool

<img src="/img/tool.gif" width="300" height="300"/>

A Graphical User Interface of the tool has been developed which contains all the functionality and features of the command line tool. The interface has been developed using the python framework pyQT. 

Like the command-line arguments, the user gets the freedom to select the config file, the operation to be performed, and cinemetrics upload feature. The home window which comes with these options to select comes in a single layout (see GIF above). The user needs to select the Film Path which is present under the `Film Path` field, and it is a mandatory field. Other fields are set with a default path as soon as the app launches except for the `Model Path` Field. When the app launches, the `Model Path` checks if there is a trained deep learning model in the path `./cutdetectorcore/trained-model/cutdetector`, if not it is kept blank, and the user needs to manually select the model path. If the mode of operation is selected as cinemetrics, it provides the option to select if the cut detection result is to be uploaded to the cinemetrics server, and further, the UI has fields of user information if the previous is selected yes. On filling all the fields, and clicking on submit, a callback is generated which calls the core cut detection file from the backend `main.py`, specifically the function `run_tool()`, with all the arguments submitted.  Once the process is completed, the user is informed of the saved file path.

The progress bar in the command line is implemented using TQDM package. I have been trying to figure out a way to add the progress bar in the user interface which will inform the user about the progress. of the process. 