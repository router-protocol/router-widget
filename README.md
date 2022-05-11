
# Router Widget

Router widget enables partners to allow their users to buy and sell any assets, on and between various blockchains in one click. Users will be able to do all this without having to leave the partner’s website.

Below is how you can integrate Router widget in your website.


## Usage/Examples
Router Widget will be integrated as `iframe`. An example of the same is given below - 
```javascript
  const baseUrl = "https://app.routerprotocol.com/swap";

  const configuration = {
    isWidget: true,
    widgetId: "widget - 0101",
    fromChain: "56",
    toChain: "137",
    fromToken: "0xe9e7CEA3DedcA5984780Bafc599bD69ADd087D56",
    toToken: "0x16ECCfDbb4eE1A85A33f3A9B21175Cd7Ae753dB4",
    dstChains: "137,56",
    dstTokens:
      "0x6855f7bb6287F94ddcC8915E37e73a3c9fEe5CF3,0x980111ae1B84E50222C8843e3A7a038F36Fecd2b",
    ctaColor: "red",
    textColor: "black",
    backgroundColor: "#3fb043",
    logoURI: "ipfs://QmaznB5PRhMC696u8yZuzN6Uwrnp7Zmfa5CydVUMvLJc9i/aDAI.svg",
  };

  const paramString = new URLSearchParams(configuration).toString();
  document.getElementById("widget__iframe").src = `${baseUrl}?${paramString}`;
```
```html
  <iframe id="widget__iframe" height="610px" width="420px" 
  src="https://app.routerprotocol.com/swap?isWidget=true&widgetId=widget-0101&fromChain=56&toChain=137&fromToken=0xe9e7CEA3DedcA5984780Bafc599bD69ADd087D56&toToken=0x16ECCfDbb4eE1A85A33f3A9B21175Cd7Ae753dB4"
  style="border: none;border-radius: 11px;box-shadow: 3px 3px 10px 4px rgba(0, 0, 0, 0.05);">
  </iframe>
```
Generate the `paramString` like given in the above example and attach it in the `src` of the `iframe`.

There are multiple parameters which can be provided to customize the widget. Partners can choose the default chains which needs to be shown on the widget along with the default tokens on both source and destination chains.

Customizable parameters need to be inserted as `query params` in `url` -

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `isWidget` | `string` | `true` **(Required)** |
| `widgetId` | `string` | Unique widgetId for each widget. Contact business team to get your uniqueId **(Required)** |
| `fromChain` | `string` | ChainId of source chain which needs to be shown as default souce chain; if not provided default souce chain will be chosen as the chain to which user's wallet is connected. In case wallet is not connected Polygon is shown as default source chain |
| `toChain` | `string` | ChainId of destination chain which needs to be shown as default destination chain. If not provided, BSC is shown as default chain |
| `fromToken` | `string` | Address of source token which needs to be shown as selected token on source chain. If not provided, USDT will be shown as default source token |
| `toToken` | `string` | Address of destination token which needs to be shown as selected token on destination chain. If not provided, USDT will be shown as default destination token |
| `ctaColor` | `string` | Color of call to action buttons |
| `textColor` | `string` | Color of all the text in the widget |
| `backgroundColor` | `string` | Background theme color of the widget |
| `logoURI` | `string` | Circular logo url, if not given original router logo will be shown |

There could be use cases where our partners might want to only show a selected list of chains for their users. We have also provided our partners with that capability; capability to restrict chains/tokens to be shown on the widget. 

Router Widget example with restiricted parameters - 
```html
  <iframe height="610px" width="420px" 
  src="https://app.routerprotocol.com/swap?isWidget=true&widgetId=widget-0101&fromChain=137&fromToken=0xc2132d05d31c914a87c6611c10748aeb04b58e8f&toChain=56&toToken=0x6855f7bb6287F94ddcC8915E37e73a3c9fEe5CF3&dstChains=137,56&dstTokens=0x6855f7bb6287F94ddcC8915E37e73a3c9fEe5CF3,0x980111ae1B84E50222C8843e3A7a038F36Fecd2b"
  style="border: none;border-radius: 11px;box-shadow: 3px 3px 10px 4px rgba(0, 0, 0, 0.05);">
  </iframe>
```

Restriction parameters are optional and can be used with the above customizable parameters as `query params` in `url`-

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `srcChains` | `string` | List of chainId's of source chains seperated by comma that needs to be shown in selection menu. Only these chains will be availbale for the users to select on the widget |
| `dstChains` | `string` | List of chainId's of destination chains seperated by comma that needs to be shown in selection menu. |
| `srcTokens` | `string` | List of addresses of source tokens belonging to list of `srcChains` seperated by comma that needs to be shown in selection menu.|
| `dstTokens` | `string` | List of addresses of destination tokens belonging to list of `dstChains` seperated by comma that needs to be shown in selection menu.|

Note - 
1. `height` and `width` are customizable but we recommend to keep the aspect ratio same.
2. In case of using restricted tokens along with restricted chain parameter, at least one token address for each restricted chain should be provided. E.g. if restricted chains on source are chosen to be Polygon and BSC and there is restriction on tokens, there will be minimum of 2 addresses of tokens needed in restricted token parameter. 1 address for Polygon chain and another for BSC chain. This will make shure that only 1 token is shown for Polygon and 1 for BSC for users to select.



