# GraphQL with .NET Core sample application

## How to start

Clone the repository and execute in the terminal following commands:

```
npm install
npm install yarn - g
yarn start
dotnet restore
dotnet run
```

Open the web browser passing URL [localhost:5000](localhost:5000) and you shall see the GraphiQL component :).

## Sample query:

```json
query ($name: String!, $withSets: Boolean!){
  plan(name: $name) {
    name,
    weeks {
      number,
      days {
        name,
      	dayOfWeek,
        sessions {
          name,
          number,
          exercises {
            name
            number,
            sets @include(if: $withSets) {
              number,
              load,
              repetitions
            }
          }
        }
      }
    }
  }
}
```

## Variables

```
{
  "name": "stronglifts",
  "withSets": true
}
```