## Guarantee
This extension shows a sum of money which the Economic Operator  may set out in 
tender documentation and which the Participant (Award of Tender/Lot) shall 
pay in case of a refusal to sign the Contract, or in other cases foreseen in 
the Law.
# Overview
The fields introduced by this extension are:
- `guarantee/currency` - The currency of the guarantee in a 3-letter ISO 4217 format. 
It should be string value.
- `guarantee/amount` - The amount of the guarantee as a number. 
It should be float value.
# Examples
The following extract illustrates these properties in use within the 
`tender/guarantee` and `lots/guarantee` block.
```
{
    "tender": {
        "id": "ocds-213czf-lots-00001-01-tender",
        "title": "Architecture and engineering services",
        "description": "The authority is seeking support to construct a new public building.",
        "procurementMethod": "open",
        "status": "active",
        "guarantee": {
          "currency": "GBP",
          "amount": 0.0
        },
        "items": [
          {
            "id": "0001",
            "description": "Architectural advice",
            "classification": {
              "scheme": "CPV",
              "id": "71210000",
              "description": "Advisory architectural services"
            },
            "relatedLot": "lot-1"
          },
          {
            "id": "0002",
            "description": "Architectural design",
            "classification": {
              "scheme": "CPV",
              "id": "71220000",
              "description": "Architectural design services"
            },
            "relatedLot": "lot-1"
          },
          {
            "id": "0003",
            "description": "Civil engineering consultant",
            "classification": {
              "scheme": "CPV",
              "id": "71311000",
              "description": "Civil engineering consultancy services"
            },
            "relatedLot": "lot-2"
          },
          {
            "id": "0004",
            "description": "Structural engineering services",
            "classification": {
              "scheme": "CPV",
              "id": "71312000",
              "description": "Structural engineering consultancy services"
            },
            "relatedLot": "lot-1"
          }
        ],
        "value": {
          "amount": 1200000,
          "currency": "GBP"
        },
        "lots": [
          {
            "id": "lot-1",
            "title": "Architectural services",
            "description": "For architectural services delivered in the project",
            "status": "active",
            "value": {
              "currency": "GBP",
              "amount": 200000
            },
            "guarantee": {
              "currency": "GBP",
              "amount": 0.0
            }
          },
          {
            "id": "lot-2",
            "title": "Civil engineering services",
            "description": "For civil engineering services delivered in the project",
            "status": "active",
            "value": {
              "currency": "GBP",
              "amount": 600000
            }
          },
          {
            "id": "lot-3",
            "title": "Structural engineering",
            "description": "For structural engineering consultancy delivered in the project",
            "status": "active",
            "value": {
              "currency": "GBP",
              "amount": 600000
            }
          }
        ],
        "lotGroups": [
          {
            "id": "lot-group-1",
            "relatedLots": [
              "lot-2",
              "lot-3"
            ],
            "optionToCombine": true,
            "maximumValue": {
              "currency": "GBP",
              "amount": 1000000
            }
          }
        ],
        "lotDetails": {
          "maximumLotsBidPerSupplier": 4,
          "maximumLotsAwardedPerSupplier": 2
        }
    }
}
```

