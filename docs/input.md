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

Use the schemas from [`https://form-input-schema.json-schema.sodaru.com/schemas/index.json`](https://form-input-schema.json-schema.sodaru.com/schemas/index.json)

### To Create new Type

Use meta-schema from [`https://form-input-schema.json-schema.sodaru.com/meta-schemas/input.json`](https://form-input-schema.json-schema.sodaru.com/meta-schemas/input.json)

## Input Types

| Input Type                                     | Data Type                                                                  |
| ---------------------------------------------- | -------------------------------------------------------------------------- |
| **Textual**                                    |                                                                            |
| [text](/schemas/text.json)                     | `string`                                                                   |
| [multiline-text](/schemas/multiline-text.json) | `string` _optionally allow **markdown**_                                   |
| [number](/schemas/number.json)                 | `number` _use **multipleOf** to support integers_                          |
| [color](/schemas/color.json)                   | `string` representing color code                                           |
| [email](/schemas/email.json)                   | `string` representing email                                                |
| [phone](/schemas/phone.json)                   | `string` representing phone number                                         |
| [password](/schemas/password.json)             | `string`                                                                   |
| [uri](/schemas/uri.json)                       | `string` representing uri                                                  |
| [json](/schemas/json.json)                     | `json` representing any json data                                          |
|                                                |                                                                            |
| **Date Time**                                  |                                                                            |
| [date](/schemas/date.json)                     | `integer`, timestamp (time part set to zero)                               |
| [time](/schemas/time.json)                     | `integer`, number of milliseconds from UTC Date                            |
| [datetime](/schemas/datetime.json)             | `integer`, complete timestamp                                              |
|                                                |                                                                            |
| **Selections**                                 |                                                                            |
| [select](/schemas/select.json)                 | `enum \| string` OR `(enum \| string)[]`                                   |
|                                                | _string_ is allowed if **allowFreeText** is true                           |
|                                                | set **multiple** to true to use multiple select                            |
|                                                |                                                                            |
| **Radios & Checkboxes**                        |                                                                            |
| [radio-group](/schemas/radio-group.json)       | `enum` max 10 items in enum, for more items use `select`                   |
| [checkbox](/schemas/checkbox.json)             | `boolean`                                                                  |
| [checkbox-group](/schemas/checkbox-group.json) | `enum[]` max 10 items in array, for more items use `select`                |
| [switch](/schemas/switch.json)                 | `boolean`                                                                  |
|                                                |                                                                            |
| **Files**                                      |                                                                            |
| [file](/schemas/file.json)                     | `string` representing id of the file                                       |
|                                                | file has to be uploaded to file server provided by **uploadUrl** attribute |
|                                                |                                                                            |
| **Others**                                     |                                                                            |
| [rating](/schemas/rating.json)                 | `number`                                                                   |
| [slider](/schemas/slider.json)                 | `number \| [number, nummber]`                                              |

## Support

This project is a part of Open Source Intitiative from [Sodaru Technologies](https://sodaru.com)

Write an email to opensource@sodaru.com for queries on this project
