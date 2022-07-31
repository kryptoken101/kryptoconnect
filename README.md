# Bridge | CoinHippo

CoinHippo Bridge is a simplified bridge app built based on [Connext's nxtp protocol](https://github.com/connext/nxtp) and subgraph technology. It is designed and built as the starter framework to be easily forked and used as the foundation of cross-chain bridge applications for any project.

<br>
<img width="1434" alt="coinhippo_bridge" src="https://user-images.githubusercontent.com/13881651/155118823-bde40bb5-e3e3-4876-8397-701424aeb47a.png">

## URLs
### Mainnet
- App: [https://bridge.coinhippo.io](https://bridge.coinhippo.io)
- Explorer: [https://connextscan.io](https://connextscan.io)
### Testnet
- App: [https://bridge-testnet.coinhippo.io](https://bridge-testnet.coinhippo.io)
- Explorer: [https://testnet.connextscan.io](https://testnet.connextscan.io)
### Connext Protocol
- Website: [https://connext.nextwork](https:/connext.nextwork)
- Doc: [https://docs.connext.network](https://docs.connext.network)

<br>

## Data provider / APIs
- [Connext Subgraph](https://github.com/connext/nxtp/tree/main/packages/subgraph)
- [Connextscan API](https://github.com/CoinHippo-Labs/connextscan-lambda)

## Technology stacks
- [Next.js](https://nextjs.org/)
- [Connext SDK](https://github.com/connext/nxtp)
- [Nomad SDK](https://github.com/nomad-xyz/nomad-monorepo)
- [web3.js](https://github.com/ChainSafe/web3.js)
- [ethers.js](https://github.com/ethers-io/ethers.js)
- [Web3Modal](https://github.com/Web3Modal/web3modal)

<br>

## Local Run
- Install dependencies
  ```
  npm install --force
  ```

- Run on [localhost:3000](http://localhost:3000)
  ```
  # mainnet
  npm run dev

  # staging
  npm run dev-dev

  # testnet
  npm run dev-testnet
  ```

<br>

## Setup your own Bridge Dapp
### modify `.env` file
  ```
  # .env for Mainnet
  # .env.staging for Mainnet Staging
  # .env.testnet for Testnet
  ```
  - ### Parameters
    - Application name & Team information
      - `NEXT_PUBLIC_APP_NAME`, `NEXT_PUBLIC_TEAM_NAME` and `NEXT_PUBLIC_TEAM_URL`

    - Application configuration
      - `NEXT_PUBLIC_NETWORK`
        - `mainnet` or `testnet`
      - `NEXT_PUBLIC_USE_CONFIG`
        - `connext` for using same configuration as [Connext](https://bridge.connext.network), the main Connext's app.
        - otherwise, use local config in [/config](/config)
      - `NEXT_PUBLIC_ANNOUNCEMENT` (optional)
        - If you're using the local config, the announcement message displayed on the app will retrieve the message from this parameter.
      - `NEXT_PUBLIC_SITE_URL`
        - the URL that your bridge is deployed on
      - `NEXT_PUBLIC_FAQ_URL` (optional)
        - the support or FAQ document URL of the bridge (`default` to Connext support document)

    - External service ID
      - `NEXT_PUBLIC_INFURA_ID`
        - using in Connect Wallet (`WalletConnectProvider` and `WalletLink`)
      - `NEXT_PUBLIC_PORTIS_ID` (optional)
        - set this parameter when you want your app to support [Portis](https://portis.io) wallet

    - Contact information
      - `NEXT_PUBLIC_TWITTER_USERNAME`, `NEXT_PUBLIC_TELEGRAM_USERNAME`, `NEXT_PUBLIC_DISCORD_URL`, `NEXT_PUBLIC_GITHUB_URL` and `NEXT_PUBLIC_ENS_NAME`

    - OG_TITLE and OG_DESCIPRTION
      - `NEXT_PUBLIC_DEFAULT_TITLE` and `NEXT_PUBLIC_DEFAULT_DESCRIPTION`

### set your App logo & image
  - [Logo](/public/logos/logo.png)
    - for dark theme: [here](/public/logos/logo_white.png)
  - [icons](/public/icons)
  - [favicon](/public/favicon.ico)
  - [App logo](/public/favicon.png) (show on MetaMask)
  - [OG_IMAGE](/public/images/ogimage.png)

### set default theme (optional)
  - [theme](/reducers/preferences): `light` or `dark`

### modify your website configuration
  - set sitemap config at [sitemap.xml](/public/sitemap.xml)
  - change sitemap url in [robots.txt](/public/robots.txt)
  - set up manifest at [manifest.json](/public/manifest.json)

### modify your package.json
  - name
  - version
  - scripts
  - etc.

 Now you are ready to deploy your Dapp. Enjoy! :)
