# euphonics

## Usage
Simply run the "format_euphonics" function on your desired input_file and output_file. 
Bear in mind that the altered sentences will be appended to the output_file so said file should be empty / not exist before function is run.

### Example
```
with open("input.conllu", "r") as file:
    format_euphonics(file, "output.conllu") # output file is created when function is run
```
