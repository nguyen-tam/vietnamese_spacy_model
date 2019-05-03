# Vietnamese Spacy Model tutorial

When searching for Vietnamese Spacy Model, I found this [vivi_spacy](https://github.com/trungtv/vivi_spacy). However it doesn't work with python 3.6. Here is the tutorial to build Vietnamese Spacy Model for python 3.6 yourself, I added the model I built on the repository too.

# Steps

Clone The Vietnamese UD treebank 

```sh
$ git clone https://github.com/UniversalDependencies/UD_Vietnamese-VTB.git
```

Make a new folder, you can change vtb-json to whatever you want
 
```
$ mkdir vtb-json
```

Convert the conllu file to json format. By default spacy generated jsonl format, so we have to add "-t json"

```
$ python -m spacy convert -t json UD_Vietnamese-VTB/vi_vtb-ud-train.conllu vtb-json/
$ python -m spacy convert -t json UD_Vietnamese-VTB/vi_vtb-ud-dev.conllu vtb-json/
```

Make a new folder for the model

````
$ mkdir vi_core_test_md
````

Then build the model

````
$ python -m spacy train vi vi_core_test_md vtb-json/vi_vtb-ud-train.json vtb-json/vi_vtb-ud-dev.json
````

Now you got the model yourself

License
----

MIT
