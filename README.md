# products-rest-api
Demonstrates use of serverless framework for Rest API creation.

use 'serverless deploy' after setting AWS credentials (https://serverless.com/framework/docs/providers/aws/guide/credentials/)

node version > 8
serverless version 1.36.0 or higher

We can see our API Gateway endpoints at the end of the deployment logs. It should look something like this:

REST API resources:
  POST - https://3412ssa.execute-api.us-east-1.amazonaws.com/dev/products
  GET - https://3412ssa.execute-api.us-east-1.amazonaws.com/dev/producst
  GET - https://3412ssa.execute-api.us-east-1.amazonaws.com/dev/products/{id}
Let's insert a new product.

We can curl our /products endpoint via POST:

curl --request POST \
  --url https://3412ssa.execute-api.us-east-1.amazonaws.com/dev/products \
  --header 'content-type: application/json' \
  --data '{
      "id": 1,
      "name": "Learning Serverless Components",
      "description": "A tutorial to learn the new Serverless Components concept.",
      "price": 15
    }'
Great! Now we should be able to get our inserted product via the following GET request:

curl https://3412ssa.execute-api.us-east-1.amazonaws.com/dev/products/1
A list of all products can be requested like this:

curl https://3412ssa.execute-api.us-east-1.amazonaws.com/dev/products
Nice! Feel free to continue playing around with your REST API.
