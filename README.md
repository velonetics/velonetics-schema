## Schema validation for Velonetics configuration files
This repository contains the source code used to publish Velonetics's configuration schema. The official Velonetics schema lives under `https://velonetics.io/schema/velonetics.json` for the **latest** version, and `https://velonetics.io/schema/vX.x/velonetics.json` for a specific version (replace `vX.x` by the version, e.g., `v2.3`)


If you are looking to validate your endpoints' JSON schema, see [JSON-schema validation](https://velonetics.io/docs/endpoints/json-schema/).

**You must use Velonetics v2.0 and higher.**

Velonetics uses this schema automatically during the `velonetics check --lint` command, but we advise you to use it in your IDE to assist you during development. Some of the features IDEs offer while working with JSON-schema is:

- Automatic validation as you type
- Show documentation of attributes
- Linting and syntax errors
- Warning for wrong types
- Autocompletion of properties

In most modern editors, **there is nothing you need to install** as they have built-in json schema validation. Visual Studio Code, Android Studio, JetBrains editors (PHPStorm, PyCharm, GoLand, WebStorm, IntelliJ IDEA...), or Eclipse, to name a few examples.

To use this schema add the `$schema` attribute in your configuration files. There is no need to clone this repo unless you'd like to submit a pull request:

    {
        "$schema": "https://velonetics.io/schema/v2.3/velonetics.json",
        "version": 3,
        "endpoints": [
            ...
        ]
    }

Replace the `v2.3` in the URL by the Velonetics version you are using.

![IDE Integration](https://velonetics.io/images/documentation/velonetics-ide-integration.png)

You can also use sub-schemas if needed. The `velonetics.json` file is the main schema that references other sub-schemas with the `$ref` attribute.

For more information visit [IDE integration](https://velonetics.io/docs/enterprise/developer/ide-integration/)

If you find any inconsistency in the schema, please **open an issue or pull request**.