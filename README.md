# Selection criteria

Adds an object to describe the criteria to qualify candidates to participate in a contracting process.

If you are using the [Lots extension](https://extensions.open-contracting.org/en/extensions/lots/master/), [follow its guidance](https://extensions.open-contracting.org/en/extensions/lots/master/#usage) on whether to use `tender.lots` fields or `tender` fields.

If your data closely follows the [Core Criterion and Core Evidence Vocabulary (CCCEV)](https://semiceu.github.io/CCCEV/), consider the [Requirements](https://extensions.open-contracting.org/en/extensions/requirements/master/) extension.

## Legal context

In the European Union, this extension's fields correspond to [eForms BG-702 (Selection Criteria) and BG-72 (Selection Criteria Second Stage Invite Number)](https://docs.ted.europa.eu/eforms/latest/reference/business-terms/). For correspondences to eForms fields, see [OCDS for eForms](https://standard.open-contracting.org/profiles/eforms/latest/en/). For correspondences to Tenders Electronic Daily (TED), see [OCDS for the European Union](http://standard.open-contracting.org/profiles/eu/latest/en/).

## Examples

### Tender

Potential suppliers and subcontractors must demonstrate a minimum of 10 years experience on similar projects.

```json
{
  "tender": {
    "selectionCriteria": {
      "criteria": [
        {
          "description": "Minimum number of years of experience on similar projects",
          "minimum": "10",
          "type": "technical",
          "appliesTo": [
            "supplier",
            "subcontractor"
          ]
        }
      ]
    }
  }
}
```

### Lot

A tender with a single lot where the selection criterion only applies for selecting candidates to be invited to the second stage of the procedure. The candidates will be selected only if the rate of their turnover over the value of the contract is at least 2.

```json
{
  "tender": {
    "lots": [
      {
        "id": "LOT-0001",
        "selectionCriteria": {
          "criteria": [
            {
              "description": "Turnover over contract value rate",
              "type": "economic",
              "forReduction": true,
              "numbers": [
                {
                  "number": 2,
                  "threshold": "minimumScore"
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
