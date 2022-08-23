## Blog 3
### Added Cinemetrics supported output format

Cinemetrics is a tool for statistical analysis of films based on the shot durations. However, Cinemetrics works on manual annotation of cut timestamps in films. 
A feature has been added to the tool 'FilmEditDetection', by which the tool is now able to generate a '.cms' file, containing cut information, which can be uploaded in the 
cinemetrics server for obtaining statistical insights into the film.

The usage of the feature has been updated in the documentation. Using it is similar to using the tool for generating other types of output, like 'CSV format of shot timestamps', or 'JSON format MEP annotation format'. An argument 'cinemetrics' is to be passed to the parameter 'operation' while running the tool.

Sample syntax : 
`python main.py --vidpath 'path/to/video' --operation 'cinemetrics'`