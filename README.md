# Member Of

Adds a `memberOf` field to describe the organizations of which an organization is a member.

The organizations referenced by the `memberOf` array should only have corresponding entries in the `parties` array if they are involved in the contracting process.

**We recommend against using this extension, unless a use case supports it, because it describes information that is generally not in the scope of a contracting process.**

## Example


```json
{
  "parties": [
    {
      "id": "12-001-52",
      "name": "SENATICS",
      "identifier": {
        "scheme": "PY-PGN",
        "id": "12-001-52",
        "legalName": "Secretaría Nacional de Tecnología y Comunicación"
      },
      "memberOf": [
        {
          "id": "12-001",
          "name": "Presidencia del Paraguay"
        }
      ]
    }
  ]
}
```

`memberOf` can be used for both direct and indirect memberships.

```json
{
  "parties": [
    {
      "id": "12-001",
      "name": "Presidencia del Paraguay",
      "identifier": {
        "scheme": "PY-PGN",
        "id": "12-001",
        "legalName": "Presidencia de la República del Paraguay"
      }
    },
    {
      "id": "12-001-52",
      "name": "SENATICS",
      "identifier": {
        "scheme": "PY-PGN",
        "id": "12-001-52",
        "legalName": "Secretaría Nacional de Tecnología y Comunicación"
      },
      "memberOf": [
        {
          "id": "12-001",
          "name": "Presidencia del Paraguay"
        },
        {
          "id": "PG",
          "name": "Government of Paraguay"
        },
        {
          "id": "PG-RBC01",
          "name": "Regional buying consortium"
        }
      ]
    }
  ]
}
```

## Issues

Report issues for this extension in the [ocds-extensions repository](https://github.com/open-contracting/ocds-extensions/issues), putting the extension's name in the issue's title.
