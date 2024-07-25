# euphonics

## Description
This function modifies all sentences in a CoNLL-U formatted file containing information about euphonics in their 10th (MISC) collumn.
More specifically, it separates the original euphonized token into two separate tokens, one without the euphonic and one for the euphonic itself.

An example, featuring a postfixed euphonic is as follows:

#### Original tokens:
```
8	μαςε	εγώ	PRON	_	Case=Gen|Number=Plur|Person=1|PronType=Prs	9	obl	_	MSeg=μας-ε|MGloss=us-euphonic
```

#### Modified tokens:
```
8-9	μαςε	_	_	_	_	_	_	_	MSeg=μας-ε|MGloss=us-euphonic
8	μας	εγώ	PRON	_	Case=Gen|Number=Plur|Person=1|PronType=Prs	10	obl	_	_
9	ε	_	_	EUPH	_	8	euph	_	_
```

## Usage
Simply run the "euphonics" function on your desired input_file and output_file. 
Bear in mind that the altered sentences will be appended to the output_file so said file should be empty / not exist before function is run.

### Example
```
with open("input.conllu", "r") as file:
    euphonics(file, "output.conllu") # output file is created when function is run
```
