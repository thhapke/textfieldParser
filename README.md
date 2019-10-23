# TextFieldParser
Getting a string from a textfield and returns the parsed content.  

## read_list
Reads a comma separated list and returns either the items or the remainder of the additional list when a text contains the modifier 'Not'. 

### Arguments
* **text** -string- from textfield that will be parsed
* **value_list** -list- list from which the parsed text elements will be removed when there is a modifier *'NOT'*. 

### Return
* List of parsed parameters

### Examples

**Simple list: **

* text = "'Hello', 'a list', separated by , me "  

-> ['Hello', 'a list', 'separated by', 'me']

**Not list**

* text = "Not Mercedes, Renault, Citroen, Peugeaut, 'Rolls Royce'" 
* value_list = ['Mercedes', 'Audi', 'VW', 'Skoda', 'Renault', 'Citroen', 'Peugeot', 'Rolls Royce']

-> ['Audi', 'VW', 'Skoda', 'Peugeot'] 
 

## read_map
Reads a comma separated list of mappings and returns a dictionary. 

### Arguments
* **text** -string- from textfield that will be parsed

### Return
* dictionary of parsed parameters

### Example
text = "'Mercedes':expensive, Audi:'sportiv', VW : 'people', Citroen:cool, 'Rolls Rocye': royal"

-> {'Mercedes': 'expensive', 'Audi': 'sportiv', 'VW': 'people', 'Citroen': 'cool', 'Rolls Rocye': 'royal'}

## read_json
Reads a json formatted string and return a dictionary 

### Arguments
* **text** -string- json-string

### Return
* dictionary of json

### Example
json_text = "{\"Luxury Class\": {\"Mercedes\":\"expensive\",\"Rolls Rocye\": \"royal\"}, \"High Middle Class\":{\"Audi\":\"sportiv\"}, \"Middle Class\" : {\"Citroen\":\"cool\",\"VW\" : \"people\" }}"

-> {'Luxury Class': {'Mercedes': 'expensive', 'Rolls Rocye': 'royal'}, 'High Middle Class': {'Audi': 'sportiv'}, 'Middle Class': {'Citroen': 'cool', 'VW': 'people'}}

## read_comparisons
Parses a list of comparisons and returns a list of lists with 3 items: (left, comparison-operator, right). There is an internal mapping of comparison characters: {'!=':'!','==':'=','>=':'≥','=>':'≥','<=':'≤','=<':'≤'} 

### Arguments
* **text** -string- Textfield string

### Return
* List of 3 element lists

### Examples

' anna > 1.70, norbert != 900, cindy <= 1.65' 

-> [['anna', '>', 1.7], ['norbert', '!', 900.0], ['cindy', '≤', 1.65]]


