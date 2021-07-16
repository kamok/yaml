https://user-images.githubusercontent.com/9758567/125991671-f2b7104c-5439-4d2b-a22b-c28e4af4df92.mov

### What?
This is a validation schema that you can use to get validations for your build.yml for RRE. This makes it so you can catch build.yml configuration errors before you push code, wait 20 minutes, and have an error show up later and realize you missed a required attribute.

Currently supports:
1. library
1. cronjob
1. microservice / grpc-microservice
1. user-interface

### How to use on VSCode:

1. Download YAML extension on VSCode

1. Add to settings.json
```
    "yaml.schemas": {
        "https://raw.githubusercontent.com/kamok/yaml/master/rre-build-yml-validation.json": [
            "*build.yml"
        ]
    },
```
The above example means all files named build.yml opened with vscode. Adjust accordingly. You might want directory specific, such as...
```
    "yaml.schemas": {
        "https://raw.githubusercontent.com/kamok/yaml/master/rre-build-yml-validation.json": [
            "yaml-test-references/**.yml",
            "cases/**.yml"
        ]
    },
```
1. Due to a bug in the yaml extensions, you need to manually trigger autocomplete with CONTROL + SPACE on fields (rather than it magically)

### How to use for other editors:
1. Find a [json schema](https://json-schema.org/understanding-json-schema/index.html) compatible processor that can interpret Supports JSON Schema 7. A json schema is a standard, like ecma script. There are implementations that parses the file, and returns an output for the editor to consume.
