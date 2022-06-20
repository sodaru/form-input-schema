# Form Input Schema

## Overview

A `Form Input` represents an User Interface to collect information from the end users

HTML defines [Input Elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Element#forms) to such User Interfaces.

Its easy to create UI when inputs are known during development. Dynamically creating the input forms will be challenging because the UI has to be creating during runtime.

An Input will have

- **User Experience** related attributes
  - theme, type of the input (text, checkbox, switch, slider, color chooser, ... etc)
- **Data Validation** related attributes
  - data-type, default value, max & min length of chars, max & min values ... etc

This project defines schema for Data Validation attributes of different types of inputs.

To Create Dynamic Forms

- a backend service can save the data matching the schemas in this project.
- an UI Utility to create UI Input Components from the dynamic data.
- dynamic form can be created by retrieving the data attributes from backend service and using the UI creation utility.

> This contains schema for all input types defined by HTML + additional input type

## Usage

Use the schemas from `https://json-schema.sodaru.com/form-input-schema/schemas/<type>.json`

### To Create new Type

Use meta-schema from `https://json-schema.sodaru.com/form-input-schema/meta-schemas/input.json`

## Input Types

| Input Type              | Data Type                                        |
| ----------------------- | ------------------------------------------------ |
| **Textual**             |                                                  |
| `text`                  | `string`                                         |
| `multiline-text`        | `string`                                         |
| `markdown`              | `string`                                         |
| `number`                | `number`                                         |
| `integer`               | `integer`                                        |
| `color`                 | `string` representing color code                 |
| `email`                 | `string` representing email                      |
| `phone`                 | `string` representing phone number               |
| `password`              | `string`                                         |
| `uri`                   | `string` representing uri                        |
|                         |                                                  |
| **Date Time**           |                                                  |
| `date`                  | `integer`, timestamp (time part set to zero)     |
| `time`                  | `integer`, number of milliseconds from UTC Date  |
| `datetime`              | `integer`, complete timestamp                    |
|                         |                                                  |
| **Selections**          |                                                  |
| `select`                | `enum \| string`                                 |
| `multiselect`           | `(enum \| string)[]`                             |
|                         | _string_ is allowed if **allowFreeText** is true |
|                         |                                                  |
| **Radios & Checkboxes** |                                                  |
| `radio`                 | `boolean`                                        |
| `radio-group`           | `enum`                                           |
| `checkbox`              | `boolean`                                        |
| `checkbox-group`        | `enum[]`                                         |
| `switch`                | `boolean`                                        |
|                         |                                                  |
| **Files**               |                                                  |
| `file`                  | `string` representing content/url of the file    |
|                         |                                                  |
| **Others**              |                                                  |
| `rating`                | `number`                                         |
| `slider`                | `number \| [number, nummber]`                    |

## Support

This project is a part of Open Source Intitiative from [Sodaru Technologies](https://sodaru.com)

Write an email to opensource@sodaru.com for queries on this project
