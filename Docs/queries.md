# SMIP Queries

In GraphQL, the endpoint is always the same, but the query payload changes to indicate the response payload you wish to retrieve. For more information on accessing the GraphQL endpoint for your SMIP instance, see the page [SMIP GraphQL Endpoint](smip-graphql.md).

## Example Queries

**<a name="query-types">Querying Equipment Types (SM Profiles)**

The following query payload returns a list of Equipment Types (also known as SM Profiles) in a given SMIP instance:

```
query equipmentTypeQuery {  
    equipmentTypes {  
        displayName, 
        subTypeOf {  
            displayName 
        }   
    } 
}
```

**<a name="query-equipment">Querying Equipment**

The following query payload returns a list of Equipment instances in a given SMIP instance:

```
query EquipmentListQuery { 
    equipments { 
        displayName, 
        id 
    }   
}
```

**<a name="query-locations">Querying Locations**

The following query payload returns a list of Locations in a given SMIP instance:

```
query placeQuery {  
    places {        
        displayName      
        partOf {        
            displayName      
        }    
    }
}
```

**<a name="query-attributes">Querying Attributes**

The following query payload returns a list of Attributes in a given SMIP instance:

```
query AttributeQuery { 
    attributes { 
        displayName, 
        id, 
        partOfId, 
        tagId 
    }  
}
```

**<a name="query-timeseries">Querying Time Series Values**

The following query payload returns a list of Time Series sample values for a given Instance Attribute Tag within the specified time range

```
query HistoryQuery {
    getRawHistoryDataWithSampling(maxSamples: 10, ids: ["1690"], startTime: "2021-02-20 00:00:00+00", endTime: "2021-02-21 00:12:00+00") {
        id
        floatvalue
        dataType
        ts
    }
}
```

## Other Operations

With GraphQL, other types of operations can be performed with special queries called Mutations. Some  [Mutation examples can be found here](mutations.md).