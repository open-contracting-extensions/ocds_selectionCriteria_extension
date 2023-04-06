# Selection Criteria

Adds an object to describe the criteria to qualify candidates to participate in a contracting process.

If you are using the [Lots extension](https://extensions.open-contracting.org/en/extensions/lots/master/), [follow its guidance](https://extensions.open-contracting.org/en/extensions/lots/master/#usage) on whether to use `tender.lots` fields or `tender` fields.

## Legal context

In the European Union, this extension's fields correspond to [eForms BG-702 (Selection Criteria) and BG-72 (Selection Criteria Second Stage Invite Number)](https://docs.ted.europa.eu/eforms/latest/reference/business-terms/). For correspondences to eForms fields, see [OCDS for eForms](https://standard.open-contracting.org/profiles/eforms/).

## Examples

### Tender

A tender with a single selection criterion.

```json
{
  "tender": {
    "selectionCriteria": {
      "criteria": [
        {
          "description": "<Description of the criterion>",
          "minimum": "<Minimum value or level of compliance>",
          "type": "technical",
          "appliesTo": [
            "supplier",
            "subcontractor"
          ],
          "numbers": [
            {
              "number": 40,
              "threshold": "minimumScore"
            }
          ]
        }
      ]
    }
  }
}
```

### Lot

A tender with a single lot where the selection criterion only applies for selecting candidates to be invited to the second stage of the procedure.

```json
{
  "tender": {
    "lots": [
      {
        "id": "LOT-0001",
        "selectionCriteria": {
          "criteria": [
            {
              "description": "A description of the criteria",
              "type": "suitability",
              "forReduction": true,
              "numbers": [
                {
                  "number": 30,
                  "weight": "percentageExact"
                }
              ]
            }
          ]
        }
      }
    ]
  }
}
```

## Issues

Report issues for this extension in the [ocds-extensions repository](https://github.com/open-contracting/ocds-extensions/issues), putting the extension's name in the issue's title.

## Changelog

### 2023-04-05

* Add `forReduction` field and `numbers` object to `SelectionCriterion`.

### 2020-07-13

* Add the `appliesTo` field.

### 2020-04-24

* Add `minProperties`, `minItems` and/or `minLength` properties.

This extension was originally discussed as part of the [OCDS for EU profile](https://github.com/open-contracting-extensions/european-union/issues) and in [pull requests](https://github.com/open-contracting-extensions/ocds_selectionCriteria_extension/pulls?q=is%3Apr+is%3Aclosed).
