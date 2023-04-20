This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `pages/index.tsx`. The page auto-updates as you edit the file.

[API routes](https://nextjs.org/docs/api-routes/introduction) can be accessed on [http://localhost:3000/api/hello](http://localhost:3000/api/hello). This endpoint can be edited in `pages/api/hello.ts`.

The `pages/api` directory is mapped to `/api/*`. Files in this directory are treated as [API routes](https://nextjs.org/docs/api-routes/introduction) instead of React pages.

This project uses [`next/font`](https://nextjs.org/docs/basic-features/font-optimization) to automatically optimize and load Inter, a custom Google Font.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.

we will-
1.index events with TheGraph
2.read them from graph

go to thegraph.com >> subgraph studio >> connect wallet >> create a subgraph >> create 'graph-nft-marketplace' subdirectory and create our local subgraph which we later push to subgraph studio
in creating a subgraph
1. we first deploy our contract on testnet then 
2. we instal graph cli using 'npm install -g @graphprotocol/graph-cli'
3. we initialise our subgraph using 'graph init --studio nft-marketplace'
4. we first define the events and customised entities to be created when an event is fired in 'schema.graphql and run 'graph codegen'
5. in src>mapping.ts we tell subgraph how to listen to the events i.e define handler functions for different events of our contract. For each event in our contract we define a separate event handler function
6. we link different events with their corresponding event handler in subgraph.yaml
7. we specify the startBlock in (subgraph.yaml>>fataSOurces>>sourcestartBlock) where we want to start indexing and this block number we get from etherscan by pasting the addresss of our contract
8. run authentication code from our graph studio (graph auth --studio a59d3b4e9bd62f38ad2a093100c7cd64)
9. we have playground on our subgraph studio where we can run some queries to see responses from our graphql
10. run query from our frontend to grab data from the graph by creating graphExample.js in pages dir
11. wrap our app in appolo client provider in _app.js to use apollo client to query the graph