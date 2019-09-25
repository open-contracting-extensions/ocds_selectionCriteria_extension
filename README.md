# Selection Criteria

Adds an object to describe the criteria to qualify candidates to participate in a contracting process.

## Legal context

In the European Union, this extension's fields correspond to [eForms BG-702 (Selection Criteria)](https://github.com/eForms/eForms). See [OCDS for the European Union](http://standard.open-contracting.org/profiles/eu/master/en/) for the correspondences to Tenders Electronic Daily (TED).

## Examples

```json
{
  "tender": {
    "selectionCriteria": {
      "criteria": [
        {
          "description": "<Description of the criterion>",
          "minimum": "<Minimum value or level of compliance>",
          "type": "technical"
        },
        {
          "description": "<Description of the criterion>",
          "minimum": "<Minimum value or level of compliance>",
          "type": "economic"
        }
      ]
    }
  }
}
```

## Issues

Report issues for this extension in the [ocds-extensions repository](https://github.com/open-contracting/ocds-extensions/issues), putting the extension's name in the issue's title.
