Add to settings.json
```
    "yaml.schemas": {
        "/Users/kamok/Documents/code/yaml-validation-demo/rre-build-yml-validation.json": [
            "*build.yml",
            "yaml-test-references/**.yml"
        ]
    },
```

Style:
Duplication of definitions are placed in defs
Singletons (such as schedule for cronjob), remain declared once