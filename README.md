## VTL Programming Guide/Reference
VTL is a logical template language, giving us power to manipulate both the request and the response in the 
standard request/response flow of a web application using techniques such as:
- Default values for new items
- Input validation and formatting
- Transforming and shaping data
- Iterating over lists, maps, and arrays to pluck out or alter values
- Filter/change responses based on user identity
- Complex authorization checks

### How is VTL used
- AWS AppSync uses VTL to translate GraphQL requests from clients into a request to our data source.

### Setup/Objective
- We create a simple GraphQL schema as below
```js
type Query {
    get(id: ID, meta: String): Thing
}

type Thing {
    id: ID!
    title: String!
    meta: String
}

schema {
    query: Query
}
```
- We pass a map of values to a Lambda function which prints out the values and then responds with them.
- It will help us understand the request/response flow and various programming techniques.
