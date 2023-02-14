# Case Conversion functions
Many tools expect to recieve inputs in specific formats.  
When we are recieving data values from certain sources, we may need to convert these values between formats which can be challenging at times.  

The key formats we see being used are:
1. Camel Case (eg. thisIsCameCase)
2. Pascal Case (eg. ThisIsPascalCase)
3. Kebab Case (eg. this-is-kebab-case)
4. Snake Case (eg this_is_snake_case)
5. Spaces (eg. this is spaced text)

This example includes 20 functions overall to help convert between those 5 types of text input:

### Convert From Camel Case
* camelToPascalCase
* camelToKebabCase
* camelToSnakeCase
* camelToSpaces

### Convert From Pascal Case
* pascalToCamelCase
* pascalToKebabCase
* pascalToSnakeCase
* pascalToSpaces

### Convert From Kebab Case
* kebabToCamelCase
* kebabToPascalCase
* kebabToSnakeCase
* kebabToSpaces

### Convert From Snake Case
* snakeToCamelCase
* snakeToPascalCase
* snakeToKebabCase
* snakeToSpaces

### Convert From Spaced Text
* spacesToCamelCase
* spacesToPascalCase
* spacesToKebabCase
* spacesToSnakeCase

# Sample Data Values
```yaml
#@data/values
---
snake_input: this_is_an_input_in_snake_case
kebab_input: this-is-an-input-in-kebab-case
camel_input: thisIsAnInputInCamelCase
pascal_input: ThisIsAnInputInPascalCase
spaces_input: "this is an input using spaces"
```
