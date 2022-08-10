# Form Input Schema

> Forms are the basic method of capturing user input

`Form Input Schema` is a platform agnostic way to define the form to collect the user inputs.

`Form Input schema` defines

- The Input collection method  
   example:- `text`, `select`, `color`, `file`,... etc
- The Validation for the Input
- Name, Label and Helper Text for the inputs
- Grouping of Similar Inputs

## Documentation

https://docs.form-input-schema.json-schema.sodaru.com

## Use Cases

- The Product Owner / Designer can define the form in the platform independent way. Individual Client (Web / Mobile / Desktop) developers can dynamically create the User Interface from the form input schema
- In case of generating Dynamic Forms, the dynamic form configuration can be saved using the form input schema

## Usage

The JSON Schema for the form input is available at https://form-input-schema.json-schema.sodaru.com/schemas/index.json

```json
{
  "inputs": {
    "user.name": {
      "type": "text",
      "label": "Name"
    },
    "user.email": {
      "type": "email",
      "label": "Email"
    },
    "user.dob": {
      "type": "date",
      "label": "Date of Birth"
    }
  },
  "schema": {
    "type": "object",
    "additionalProperties": "false",
    "properties": {
      "user.name": {
        "type": "string"
      },
      "user.email": {
        "type": "string",
        "format": "email"
      },
      "user.dob": {
        "type": "number"
      }
    }
  }
}
```
