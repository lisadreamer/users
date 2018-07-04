# users
studying graphql

Installation
------------
npm install

Run
---
npm run dev
npm run json:server

Use
---
http://localhost:4000/graphql  - graphiql

http://localhost:3000          - json server

run in graphiql. Example:

query company{
  company(id:"1") {
    id
    name
    description
  }
}

query user{
  user(id:"18") {
    fName,
    company {
      id
    }
  }
}

query co{
  co1: company(id:"1") {
    ...co
  }
  co2: company(id:"2") {
    ...co
  }
}
fragment co on Company{
  id
  name
  description
  users{
    fName
  }
}

mutation addUser{
  addUser(fName: "Alex", age: 18) {
    id
    fName
    age
  }
}

mutation editUser{
  editUser(id: "write_an_id", fName: "George", companyId: "2") {
    id
    fName
    age
    company{
      name
    }
  }
}

mutation deleteUser{
  deleteUser(id: "write_an_id") {
    id
  }
}
