# Member Of to party extension

## Description

The party.memberOf property can be used to indicate the relationship between a party 
and some other party, association or grouping.

Is not require that the party identified by memberOf.id exists in the parties array, 
but implementations could choose to include it, so that it is possible to represent 
a tree-structure of multi-level hierarchy. A memberOf object should not be an object 
in the parties array unless it is semantically a party i.e. "involved in the contracting 
process". If the party is only referred to by memberOf, 
that's an indication that it's probably not involved in the contracting process.

We strongly recommend against populating memberOf unless a use case supports it.

## Example 1
```javascript
{
  "parties":[
    {
      "id": "12-001-52",
      "name": "SENATICS",
      "identifier": {
        "scheme": "PY-PGN",
        "id": "12-001-52",
        "legalName": "Secretaría Nacional de Tecnología y Comunicación"
      },
      "memberOf": [{
        "id": "12-001",
        "name": "Presidencia del Paraguay"
      }]
    }
  ]
}
```

## Example 2
```javascript
{
  "parties": [
    {
      "id": "12-001",
      "name": "Presidencia de Paraguay",
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
      "memberOf": [{
        "id": "12-001",
        "name": "Presidencia del Paraguay"
      },
       {
        "id":"PG",
        "name":"Government of Paraguay"
       },
      {
       "id":"PG-RBC01",
       "name":"Regional buying consortium"
      }]
    }
  ]
}
```

The example above also shows how memberOf can be used to represent arbitrary 
memberships - and does not have to only relate parties, but can relate a party to an 
association. memberOf is also not restricted to declaring direct parents, 
but might also be used to declare the top parent of an organisation.

## Issues

Report issues for this extension in the [ocds-extensions repository](https://github.com/open-contracting/ocds-extensions/issues), putting the extension's name in the issue's title.
