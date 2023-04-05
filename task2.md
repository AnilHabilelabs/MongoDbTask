## without indexing

> db.getCollection("restaurants").find({borough:"Brooklyn"}).explain(true)

```
{
    "explainVersion" : "1",
    "queryPlanner" : {
        "namespace" : "sample_restaurants.restaurants",
        "indexFilterSet" : false,
        "parsedQuery" : {
            "borough" : {
                "$eq" : "Brooklyn"
            }
        },
        "queryHash" : "A1445303",
        "planCacheKey" : "A1445303",
        "maxIndexedOrSolutionsReached" : false,
        "maxIndexedAndSolutionsReached" : false,
        "maxScansToExplodeReached" : false,
        "winningPlan" : {
            "stage" : "COLLSCAN",
            "filter" : {
                "borough" : {
                    "$eq" : "Brooklyn"
                }
            },
            "direction" : "forward"
        },
        "rejectedPlans" : [

        ]
    },
    "executionStats" : {
        "executionSuccess" : true,
        "nReturned" : 6086.0,
        "executionTimeMillis" : 82.0,
        "totalKeysExamined" : 0.0,
        "totalDocsExamined" : 25359.0,
        "executionStages" : {
            "stage" : "COLLSCAN",
            "filter" : {
                "borough" : {
                    "$eq" : "Brooklyn"
                }
            },
            "nReturned" : 6086.0,
            "executionTimeMillisEstimate" : 29.0,
            "works" : 25361.0,
            "advanced" : 6086.0,
            "needTime" : 19274.0,
            "needYield" : 0.0,
            "saveState" : 25.0,
            "restoreState" : 25.0,
            "isEOF" : 1.0,
            "direction" : "forward",
            "docsExamined" : 25359.0
        },
        "allPlansExecution" : [

        ]
    },
    "command" : {
        "find" : "restaurants",
        "filter" : {
            "borough" : "Brooklyn"
        },
        "$db" : "sample_restaurants"
    },
    "serverInfo" : {
        "host" : "Anilkumar",
        "port" : 27017.0,
        "version" : "6.0.5",
        "gitVersion" : "c9a99c120371d4d4c52cbb15dac34a36ce8d3b1d"
    },
    "serverParameters" : {
        "internalQueryFacetBufferSizeBytes" : 104857600.0,
        "internalQueryFacetMaxOutputDocSizeBytes" : 104857600.0,
        "internalLookupStageIntermediateDocumentMaxSizeBytes" : 104857600.0,
        "internalDocumentSourceGroupMaxMemoryBytes" : 104857600.0,
        "internalQueryMaxBlockingSortMemoryUsageBytes" : 104857600.0,
        "internalQueryProhibitBlockingMergeOnMongoS" : 0.0,
        "internalQueryMaxAddToSetBytes" : 104857600.0,
        "internalDocumentSourceSetWindowFieldsMaxMemoryBytes" : 104857600.0
    },
    "ok" : 1.0
}

```

## with index

> db.restaurants.createIndex({borough:1})

```
{
    "explainVersion" : "1",
    "queryPlanner" : {
        "namespace" : "sample_restaurants.restaurants",
        "indexFilterSet" : false,
        "parsedQuery" : {
            "borough" : {
                "$eq" : "Brooklyn"
            }
        },
        "queryHash" : "A1445303",
        "planCacheKey" : "BFEA32E5",
        "maxIndexedOrSolutionsReached" : false,
        "maxIndexedAndSolutionsReached" : false,
        "maxScansToExplodeReached" : false,
        "winningPlan" : {
            "stage" : "FETCH",
            "inputStage" : {
                "stage" : "IXSCAN",
                "keyPattern" : {
                    "borough" : 1.0
                },
                "indexName" : "borough_1",
                "isMultiKey" : false,
                "multiKeyPaths" : {
                    "borough" : [

                    ]
                },
                "isUnique" : false,
                "isSparse" : false,
                "isPartial" : false,
                "indexVersion" : 2.0,
                "direction" : "forward",
                "indexBounds" : {
                    "borough" : [
                        "[\"Brooklyn\", \"Brooklyn\"]"
                    ]
                }
            }
        },
        "rejectedPlans" : [

        ]
    },
    "executionStats" : {
        "executionSuccess" : true,
        "nReturned" : 6086.0,
        "executionTimeMillis" : 14.0,
        "totalKeysExamined" : 6086.0,
        "totalDocsExamined" : 6086.0,
        "executionStages" : {
            "stage" : "FETCH",
            "nReturned" : 6086.0,
            "executionTimeMillisEstimate" : 3.0,
            "works" : 6087.0,
            "advanced" : 6086.0,
            "needTime" : 0.0,
            "needYield" : 0.0,
            "saveState" : 6.0,
            "restoreState" : 6.0,
            "isEOF" : 1.0,
            "docsExamined" : 6086.0,
            "alreadyHasObj" : 0.0,
            "inputStage" : {
                "stage" : "IXSCAN",
                "nReturned" : 6086.0,
                "executionTimeMillisEstimate" : 3.0,
                "works" : 6087.0,
                "advanced" : 6086.0,
                "needTime" : 0.0,
                "needYield" : 0.0,
                "saveState" : 6.0,
                "restoreState" : 6.0,
                "isEOF" : 1.0,
                "keyPattern" : {
                    "borough" : 1.0
                },
                "indexName" : "borough_1",
                "isMultiKey" : false,
                "multiKeyPaths" : {
                    "borough" : [

                    ]
                },
                "isUnique" : false,
                "isSparse" : false,
                "isPartial" : false,
                "indexVersion" : 2.0,
                "direction" : "forward",
                "indexBounds" : {
                    "borough" : [
                        "[\"Brooklyn\", \"Brooklyn\"]"
                    ]
                },
                "keysExamined" : 6086.0,
                "seeks" : 1.0,
                "dupsTested" : 0.0,
                "dupsDropped" : 0.0
            }
        },
        "allPlansExecution" : [

        ]
    },
    "command" : {
        "find" : "restaurants",
        "filter" : {
            "borough" : "Brooklyn"
        },
        "$db" : "sample_restaurants"
    },
    "serverInfo" : {
        "host" : "Anilkumar",
        "port" : 27017.0,
        "version" : "6.0.5",
        "gitVersion" : "c9a99c120371d4d4c52cbb15dac34a36ce8d3b1d"
    },
    "serverParameters" : {
        "internalQueryFacetBufferSizeBytes" : 104857600.0,
        "internalQueryFacetMaxOutputDocSizeBytes" : 104857600.0,
        "internalLookupStageIntermediateDocumentMaxSizeBytes" : 104857600.0,
        "internalDocumentSourceGroupMaxMemoryBytes" : 104857600.0,
        "internalQueryMaxBlockingSortMemoryUsageBytes" : 104857600.0,
        "internalQueryProhibitBlockingMergeOnMongoS" : 0.0,
        "internalQueryMaxAddToSetBytes" : 104857600.0,
        "internalDocumentSourceSetWindowFieldsMaxMemoryBytes" : 104857600.0
    },
    "ok" : 1.0
}
```

## without compound index

> db.getCollection("restaurants").find({borough:"Brooklyn",cuisine:"American"}).explain(true)

```
{
    "explainVersion" : "1",
    "queryPlanner" : {
        "namespace" : "sample_restaurants.restaurants",
        "indexFilterSet" : false,
        "parsedQuery" : {
            "$and" : [
                {
                    "borough" : {
                        "$eq" : "Brooklyn"
                    }
                },
                {
                    "cuisine" : {
                        "$eq" : "American"
                    }
                }
            ]
        },
        "queryHash" : "FB4A051B",
        "planCacheKey" : "A206100B",
        "maxIndexedOrSolutionsReached" : false,
        "maxIndexedAndSolutionsReached" : false,
        "maxScansToExplodeReached" : false,
        "winningPlan" : {
            "stage" : "FETCH",
            "filter" : {
                "cuisine" : {
                    "$eq" : "American"
                }
            },
            "inputStage" : {
                "stage" : "IXSCAN",
                "keyPattern" : {
                    "borough" : 1.0
                },
                "indexName" : "borough_1",
                "isMultiKey" : false,
                "multiKeyPaths" : {
                    "borough" : [

                    ]
                },
                "isUnique" : false,
                "isSparse" : false,
                "isPartial" : false,
                "indexVersion" : 2.0,
                "direction" : "forward",
                "indexBounds" : {
                    "borough" : [
                        "[\"Brooklyn\", \"Brooklyn\"]"
                    ]
                }
            }
        },
        "rejectedPlans" : [

        ]
    },
    "executionStats" : {
        "executionSuccess" : true,
        "nReturned" : 1273.0,
        "executionTimeMillis" : 14.0,
        "totalKeysExamined" : 6086.0,
        "totalDocsExamined" : 6086.0,
        "executionStages" : {
            "stage" : "FETCH",
            "filter" : {
                "cuisine" : {
                    "$eq" : "American"
                }
            },
            "nReturned" : 1273.0,
            "executionTimeMillisEstimate" : 1.0,
            "works" : 6087.0,
            "advanced" : 1273.0,
            "needTime" : 4813.0,
            "needYield" : 0.0,
            "saveState" : 6.0,
            "restoreState" : 6.0,
            "isEOF" : 1.0,
            "docsExamined" : 6086.0,
            "alreadyHasObj" : 0.0,
            "inputStage" : {
                "stage" : "IXSCAN",
                "nReturned" : 6086.0,
                "executionTimeMillisEstimate" : 1.0,
                "works" : 6087.0,
                "advanced" : 6086.0,
                "needTime" : 0.0,
                "needYield" : 0.0,
                "saveState" : 6.0,
                "restoreState" : 6.0,
                "isEOF" : 1.0,
                "keyPattern" : {
                    "borough" : 1.0
                },
                "indexName" : "borough_1",
                "isMultiKey" : false,
                "multiKeyPaths" : {
                    "borough" : [

                    ]
                },
                "isUnique" : false,
                "isSparse" : false,
                "isPartial" : false,
                "indexVersion" : 2.0,
                "direction" : "forward",
                "indexBounds" : {
                    "borough" : [
                        "[\"Brooklyn\", \"Brooklyn\"]"
                    ]
                },
                "keysExamined" : 6086.0,
                "seeks" : 1.0,
                "dupsTested" : 0.0,
                "dupsDropped" : 0.0
            }
        },
        "allPlansExecution" : [

        ]
    },
    "command" : {
        "find" : "restaurants",
        "filter" : {
            "borough" : "Brooklyn",
            "cuisine" : "American"
        },
        "$db" : "sample_restaurants"
    },
    "serverInfo" : {
        "host" : "Anilkumar",
        "port" : 27017.0,
        "version" : "6.0.5",
        "gitVersion" : "c9a99c120371d4d4c52cbb15dac34a36ce8d3b1d"
    },
    "serverParameters" : {
        "internalQueryFacetBufferSizeBytes" : 104857600.0,
        "internalQueryFacetMaxOutputDocSizeBytes" : 104857600.0,
        "internalLookupStageIntermediateDocumentMaxSizeBytes" : 104857600.0,
        "internalDocumentSourceGroupMaxMemoryBytes" : 104857600.0,
        "internalQueryMaxBlockingSortMemoryUsageBytes" : 104857600.0,
        "internalQueryProhibitBlockingMergeOnMongoS" : 0.0,
        "internalQueryMaxAddToSetBytes" : 104857600.0,
        "internalDocumentSourceSetWindowFieldsMaxMemoryBytes" : 104857600.0
    },
    "ok" : 1.0
}

```

## with compound indexing

> db.restaurants.createIndex({borough:1,cuisine:1})

```
{
    "explainVersion" : "1",
    "queryPlanner" : {
        "namespace" : "sample_restaurants.restaurants",
        "indexFilterSet" : false,
        "parsedQuery" : {
            "$and" : [
                {
                    "borough" : {
                        "$eq" : "Brooklyn"
                    }
                },
                {
                    "cuisine" : {
                        "$eq" : "American"
                    }
                }
            ]
        },
        "queryHash" : "FB4A051B",
        "planCacheKey" : "91C030C4",
        "maxIndexedOrSolutionsReached" : false,
        "maxIndexedAndSolutionsReached" : false,
        "maxScansToExplodeReached" : false,
        "winningPlan" : {
            "stage" : "FETCH",
            "inputStage" : {
                "stage" : "IXSCAN",
                "keyPattern" : {
                    "borough" : 1.0,
                    "cuisine" : 1.0
                },
                "indexName" : "borough_1_cuisine_1",
                "isMultiKey" : false,
                "multiKeyPaths" : {
                    "borough" : [

                    ],
                    "cuisine" : [

                    ]
                },
                "isUnique" : false,
                "isSparse" : false,
                "isPartial" : false,
                "indexVersion" : 2.0,
                "direction" : "forward",
                "indexBounds" : {
                    "borough" : [
                        "[\"Brooklyn\", \"Brooklyn\"]"
                    ],
                    "cuisine" : [
                        "[\"American\", \"American\"]"
                    ]
                }
            }
        },
        "rejectedPlans" : [
            {
                "stage" : "FETCH",
                "filter" : {
                    "cuisine" : {
                        "$eq" : "American"
                    }
                },
                "inputStage" : {
                    "stage" : "IXSCAN",
                    "keyPattern" : {
                        "borough" : 1.0
                    },
                    "indexName" : "borough_1",
                    "isMultiKey" : false,
                    "multiKeyPaths" : {
                        "borough" : [

                        ]
                    },
                    "isUnique" : false,
                    "isSparse" : false,
                    "isPartial" : false,
                    "indexVersion" : 2.0,
                    "direction" : "forward",
                    "indexBounds" : {
                        "borough" : [
                            "[\"Brooklyn\", \"Brooklyn\"]"
                        ]
                    }
                }
            }
        ]
    },
    "executionStats" : {
        "executionSuccess" : true,
        "nReturned" : 1273.0,
        "executionTimeMillis" : 5.0,
        "totalKeysExamined" : 1273.0,
        "totalDocsExamined" : 1273.0,
        "executionStages" : {
            "stage" : "FETCH",
            "nReturned" : 1273.0,
            "executionTimeMillisEstimate" : 0.0,
            "works" : 1274.0,
            "advanced" : 1273.0,
            "needTime" : 0.0,
            "needYield" : 0.0,
            "saveState" : 1.0,
            "restoreState" : 1.0,
            "isEOF" : 1.0,
            "docsExamined" : 1273.0,
            "alreadyHasObj" : 0.0,
            "inputStage" : {
                "stage" : "IXSCAN",
                "nReturned" : 1273.0,
                "executionTimeMillisEstimate" : 0.0,
                "works" : 1274.0,
                "advanced" : 1273.0,
                "needTime" : 0.0,
                "needYield" : 0.0,
                "saveState" : 1.0,
                "restoreState" : 1.0,
                "isEOF" : 1.0,
                "keyPattern" : {
                    "borough" : 1.0,
                    "cuisine" : 1.0
                },
                "indexName" : "borough_1_cuisine_1",
                "isMultiKey" : false,
                "multiKeyPaths" : {
                    "borough" : [

                    ],
                    "cuisine" : [

                    ]
                },
                "isUnique" : false,
                "isSparse" : false,
                "isPartial" : false,
                "indexVersion" : 2.0,
                "direction" : "forward",
                "indexBounds" : {
                    "borough" : [
                        "[\"Brooklyn\", \"Brooklyn\"]"
                    ],
                    "cuisine" : [
                        "[\"American\", \"American\"]"
                    ]
                },
                "keysExamined" : 1273.0,
                "seeks" : 1.0,
                "dupsTested" : 0.0,
                "dupsDropped" : 0.0
            }
        },
        "allPlansExecution" : [
            {
                "nReturned" : 101.0,
                "executionTimeMillisEstimate" : 0.0,
                "totalKeysExamined" : 101.0,
                "totalDocsExamined" : 101.0,
                "score" : 2.0002,
                "executionStages" : {
                    "stage" : "FETCH",
                    "nReturned" : 101.0,
                    "executionTimeMillisEstimate" : 0.0,
                    "works" : 101.0,
                    "advanced" : 101.0,
                    "needTime" : 0.0,
                    "needYield" : 0.0,
                    "saveState" : 0.0,
                    "restoreState" : 0.0,
                    "isEOF" : 0.0,
                    "docsExamined" : 101.0,
                    "alreadyHasObj" : 0.0,
                    "inputStage" : {
                        "stage" : "IXSCAN",
                        "nReturned" : 101.0,
                        "executionTimeMillisEstimate" : 0.0,
                        "works" : 101.0,
                        "advanced" : 101.0,
                        "needTime" : 0.0,
                        "needYield" : 0.0,
                        "saveState" : 0.0,
                        "restoreState" : 0.0,
                        "isEOF" : 0.0,
                        "keyPattern" : {
                            "borough" : 1.0,
                            "cuisine" : 1.0
                        },
                        "indexName" : "borough_1_cuisine_1",
                        "isMultiKey" : false,
                        "multiKeyPaths" : {
                            "borough" : [

                            ],
                            "cuisine" : [

                            ]
                        },
                        "isUnique" : false,
                        "isSparse" : false,
                        "isPartial" : false,
                        "indexVersion" : 2.0,
                        "direction" : "forward",
                        "indexBounds" : {
                            "borough" : [
                                "[\"Brooklyn\", \"Brooklyn\"]"
                            ],
                            "cuisine" : [
                                "[\"American\", \"American\"]"
                            ]
                        },
                        "keysExamined" : 101.0,
                        "seeks" : 1.0,
                        "dupsTested" : 0.0,
                        "dupsDropped" : 0.0
                    }
                }
            },
            {
                "nReturned" : 36.0,
                "executionTimeMillisEstimate" : 0.0,
                "totalKeysExamined" : 101.0,
                "totalDocsExamined" : 101.0,
                "score" : 1.3566356435643563,
                "executionStages" : {
                    "stage" : "FETCH",
                    "filter" : {
                        "cuisine" : {
                            "$eq" : "American"
                        }
                    },
                    "nReturned" : 36.0,
                    "executionTimeMillisEstimate" : 0.0,
                    "works" : 101.0,
                    "advanced" : 36.0,
                    "needTime" : 65.0,
                    "needYield" : 0.0,
                    "saveState" : 1.0,
                    "restoreState" : 0.0,
                    "isEOF" : 0.0,
                    "docsExamined" : 101.0,
                    "alreadyHasObj" : 0.0,
                    "inputStage" : {
                        "stage" : "IXSCAN",
                        "nReturned" : 101.0,
                        "executionTimeMillisEstimate" : 0.0,
                        "works" : 101.0,
                        "advanced" : 101.0,
                        "needTime" : 0.0,
                        "needYield" : 0.0,
                        "saveState" : 1.0,
                        "restoreState" : 0.0,
                        "isEOF" : 0.0,
                        "keyPattern" : {
                            "borough" : 1.0
                        },
                        "indexName" : "borough_1",
                        "isMultiKey" : false,
                        "multiKeyPaths" : {
                            "borough" : [

                            ]
                        },
                        "isUnique" : false,
                        "isSparse" : false,
                        "isPartial" : false,
                        "indexVersion" : 2.0,
                        "direction" : "forward",
                        "indexBounds" : {
                            "borough" : [
                                "[\"Brooklyn\", \"Brooklyn\"]"
                            ]
                        },
                        "keysExamined" : 101.0,
                        "seeks" : 1.0,
                        "dupsTested" : 0.0,
                        "dupsDropped" : 0.0
                    }
                }
            }
        ]
    },
    "command" : {
        "find" : "restaurants",
        "filter" : {
            "borough" : "Brooklyn",
            "cuisine" : "American"
        },
        "$db" : "sample_restaurants"
    },
    "serverInfo" : {
        "host" : "Anilkumar",
        "port" : 27017.0,
        "version" : "6.0.5",
        "gitVersion" : "c9a99c120371d4d4c52cbb15dac34a36ce8d3b1d"
    },
    "serverParameters" : {
        "internalQueryFacetBufferSizeBytes" : 104857600.0,
        "internalQueryFacetMaxOutputDocSizeBytes" : 104857600.0,
        "internalLookupStageIntermediateDocumentMaxSizeBytes" : 104857600.0,
        "internalDocumentSourceGroupMaxMemoryBytes" : 104857600.0,
        "internalQueryMaxBlockingSortMemoryUsageBytes" : 104857600.0,
        "internalQueryProhibitBlockingMergeOnMongoS" : 0.0,
        "internalQueryMaxAddToSetBytes" : 104857600.0,
        "internalDocumentSourceSetWindowFieldsMaxMemoryBytes" : 104857600.0
    },
    "ok" : 1.0
}

```
