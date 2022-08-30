## Blog 4
### Added feature to upload results to Cinemetrics Server

This is a feature added newly to the tool, which involves upload the cut detection results of the film to the cinemetrics server, the further analysis of the film are available at [http://www.cinemetrics.lv/database.php]. 

The feature is implemented by calling the `get_cinemetrics`, present in the run.py file. Like any other `get_X` function, this function calls the background packages to run over the film and get a list of hardcuts and softcuts by calling the fucntion `predict().run()`. The list of hardcuts, and softcuts are then passed to `cinemetrics` function where a python dictionary is generated with the obtained hardcut and softcut results. Cinemetrics happens to take a specific list of data as a POST request. Hence, the generated python dictionary is sent to the cinemetrics server as POST request using the `requests` package.

Using this feature also demands some change in the command line syntax of the tool, because Cinemetrics wants to be provided with some submitter imformation. The following syntax can be used : 

`python main.py --vidpath <path/to/video> --modpath <path/to/model> --operation <result_output_format> --config <path/to/config> --config <path/to/config> --cinemetrics_submit --yname <submitter name> --mtitle <movie_title> --myear <movie_year> --email <submitter_email>`

Previosuly the tool saved output in one of already specified locations like './json_mep', './cuts', './shots', './cinemetrics' according to the type of operation the user wants to perform. A feature has been implemented in the latest commit which includes customising the out directory of the generate result file. This is done by overwriting the previous output directory `outdir` with the user-input output directory in `run.py`. 

python main.py --vidpath <path/to/video> --modpath <path/to/model> --operation <result_output_format> --oudir <path/to/output/directory> --config <path/to/config>