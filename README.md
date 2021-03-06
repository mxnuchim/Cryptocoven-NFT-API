![Alt text](https://github.com/mxnuchim/Cryptocoven-NFT-API/blob/main/headerimage.png)

# Cryptocoven-NFT-API
This is the code for an NFT smart contract API with filtering, sorting, full text search and relationships using GraphQL
[Cryptocoven smart contract transactions on etherscan] (https://etherscan.io/address/0x5180db8F5c931aaE63c74266b211F580155ecac8) 

# How to use the API
[Link to my subgraph on thegraph.com] (https://thegraph.com/hosted-service/subgraph/mxnuchim/xcryptocoven) <br />
You can try some of these queries out there

## Example query:

```
{
  tokens(first: 5) {
    id
    tokenID
    tokenURI
    externalURL
    image 
    name 
    description
    type 
    sun 
    moon 
    rising 
    updatedAtTimestamp 
    owner {
      id 
    }
  }
}
```
## Filtering

```
{
  tokens(
    where: {
      sun_contains: "capricorn"
    }
  ) {
    sun 
    name
  }
}
Full text search

{
  covenSearch(
    text: "'CRUSH PEARLS IN YOUR FISTS'"
  ) {
    id
    name
    description
  }
}
```
## How to deploy the API
This project is an example of how you can build and deploy Graph Protocol APIs for NFT projects.

This subgraph indexes data from Cryptocoven smart contract transactions and makes them queryable.

This API enables advanced querying capabilities like full text search, relationships between tokens and users, filtering, sorting, and pagination.

To deploy this API, follow these steps:

Clone this repo, change into the directory, and install the dependencies:
``` 
git clone https://github.com/mxnuchim/Cryptocoven-NFT-API.git

cd Cryptocoven-NFT-API

npm install
```
Visit The Graph hosted service dashboard, create a profile, and create a new subgraph by clicking Add Subgraph.

Install The Graph CLI:

```
npm install -g @graphprotocol/graph-cli
```
[Authenticate the your CLI environment with the Access Token from your account dashboard:
graph auth] (https://api.thegraph.com/deploy/)
Replace username/apiname in package.json with your username and apiname, for example: mxnuchim/xcryptocoven

Deploy the subgraph

```
yarn deploy
```
