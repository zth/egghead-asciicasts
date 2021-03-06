Instructor: [00:00] To change data with GraphQL, we use a mutation. These are named just like queries and the schema. Within the schema, we have a mutation called createAccount. Let's write that mutation.

[00:10] We're going to use the `mutation` keyword. We're going to use the name of the mutation `createAccount`. It looks it takes in something called an input, which is `createAccount` input.

```graphql
mutation {
  createAccount
}
```

[00:21] If we scroll down a little bit and click on the input, we're going to see that `createAccount` is actually a wrapper around name, user name, and password.

![Create account is a wrapper](../images/use-an-input-type-to-create-an-account-with-a-graphql-mutation-create-account.png)

 Every time I create an account, I'm going to need to provide those things.

[00:33] Now here's where the input comes in handy. Instead of sending all of these variables one at a time, I can wrap them in the input, and then I can send them as one thing.

[00:42] Here I am going to use the `input`, and I am going to pass in the `input` as a variable. We'll set this up at the top. Input is of type `CreateAccountInput`, and is non-nullable. We'll use the exclamation point. We'll set up this argument to take in the input.

```graphql
mutation ($input: CreateAccountInput!) {
  createAccount(input: $input) {}
}
```

[00:58] I'll use the query variables panel to pass in these variables, but this time we are going to put everything on that `input` key. We're going to nest in object here with `name`, with `username`, and with `password`. Now that I have these input values defined, I need to return something from this mutation.

#### Query variables panel

```graphql
{
  "input": {
    "name": "Eve Porcello",
    "username": "ep123",
    "password": "pass"
  }
}
```

[01:17] What this mutation returns is a customer object. This will give us access to all of the fields on the customer. Whenever I create my account, it's going to echo back those account details that I provided in the input. We'll ask for `username` and `name`.

[01:33] When we send this mutation, we're going to send all of the values from the input object. We're going to get back the `username` and the `name` for the customer that's just been created.

[01:42] `CreateAccount` takes in an `input` called `createAccountInput`. We pass the variables in the query variables panel, and then the mutation returns a customer object so I can access those values that I've just supplied.

![Account information returned after createAccount mutation ran](https://res.cloudinary.com/dg3gyk0gu/image/upload/v1563555710/transcript-images/egghead-use-an-input-type-to-create-an-account-with-a-graphql-mutation-account-info-returned.png)
