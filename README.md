# NAME OF APP
One sentence explanation of the tool.

## Motivation (Why did we build this?)
Why did BrightHive build this?

## Demo (or Features)
What does this tool do? Include screenshots and/or GIFs.

Alternatively, this section may enumerate the features of the app. Use bullet points.

## How to use [NAME OF APP]
[OPTIONAL] This section describes how to use the app, e.g., how to install it via `pip`, how to configure it, how to execute useful functions, etc. This section is necessary for libraries and scripts, but may not be useful for web APIs. 

## How to develop [NAME OF APP]
This section should provide instructions for running the app locally: requirements, docker, virtualenv management, etc. Future BrightHive developers need this section, in particular! But this section can also be beneficial to off-the-street open source developers. For this reason, please include the following text somewhere:

> We welcome code contributions, suggestions, and reports! Please report bugs and make suggestions using Github issues. The BrightHive team will triage and prioritize your issue as soon as possible.

## Testing
How do I run tests? (And what libraries did we use to write said tests?)

## Team
Names and titles of core contributors (including people who did not push code to Github). Use bullets, for example:

```
* Regina Compton (Software Engineer)
* Logan Ripplinger (Software Engineer)
* Sarah Henry (User Experience Researcher and Strategist)
```

## License
Include a link to the LICENSE.md file in your repo. 





# Original code
Please see branch `original-code` for the original code. This version includes some improvements and removes some features.


# How to set this repo up
Please see [this documentation](https://docs.google.com/document/d/1_Bz1zeICXzgwQC_N637CQIyxHeRwMuSV5FG7GLDO9IM/edit?usp=sharing) for indepth technical notes on how to setup this repo.

# How to use
## Extract a flat file
Open `sync_nlx` and set the variables correctly.
```
pipenv run sync_nlx.py
```

The original code compresses and pushes the flat files to S3, this version does not. It can be easily copy and pasted to add that functionality by going to the `original-code` branch.

Compress your flat file (gz preferably) and send it whereever you need to.

If instead you want to create the schema.org files continue to the next step without compressing.

## Conversion to schema.org
Set the correct variables in `nlx.py` and run
```
pipenv run nlx.py
```

# Troubleshooting
Some organizations may have trouble opening the csv files produced.

In that case you can try ASCII encoding the file and setting the row delimieter to CRLF with the following commands,
```bash
cat 2018.csv | iconv -c -t ASCII//IGNORE > 2018_ascii_dos.csv
unix2dos 2018_ascii_dos.csv
```
