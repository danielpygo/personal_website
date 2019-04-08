---
title: "GraphQL notes pt 2"
date: 2019-3-02T20:55:46-06:00
description: "Notes about graphql system"
type: "notes"
draft: false
---

## GRAPHQL BASICS
  * It is a query language to avoid under and overfetching from apis.
  * Most applications today have the need to fetch data from a server where that data is stored in a database.
  It’s the responsibility of the API to provide an interface to the stored data that fits an application’s needs.
  * ''' Increased mobile usage, low-powered devices and sloppy networks were the initial reasons why Facebook developed GraphQL.
  GraphQL minimizes the amount of data that needs to be transferred over the network and thus majorly improves applications
  operating under these conditions.'''

  When you previously used plain HTTP (like fetch in Javascript or NSURLSession on iOS) to load data from an API, all you need to do with GraphQL is write a query where you declare your data requirements and let the system take care of sending the request and handling the response for you. This is precisely what a GraphQL client will do.


So there is a Query, specifying which queries
and what they return,
then you pass that with the resolver, and it goes BFS and resolves all the nested
fields, then repackages it up. If you violate the schema, it reutnrs data and error
otherwise just data


schema-driven or schema-first development.
-Extend the GraphQL schema definition with a new root field (and new data types, if needed)
-Implement corresponding resolver functions for the added fields


Query Resolution


Can you imagine what the query resolution process now looks like? Effectively, everything the GraphQL server has to do is invoke all resolver functions for the fields that are contained in the query and then package up the response according to the query's shape. Query resolution thus merely becomes a process of orchestrating the invocation of resolver functions!
