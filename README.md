
# Router Widget

Code snippet given below to use router widget.


## Usage/Examples
Router Widget to be used as `iframe` given below - 
```html
  <iframe height="610px" width="420px" 
  src="https://app.routerprotocol.com/swap?isWidget=true&widgetId=widget-0101&fromChain=56&toChain=137&fromToken=0xe9e7CEA3DedcA5984780Bafc599bD69ADd087D56&toToken=0x16ECCfDbb4eE1A85A33f3A9B21175Cd7Ae753dB4"
  style="border: none;border-radius: 11px;box-shadow: 3px 3px 10px 4px rgba(0, 0, 0, 0.05);">
  </iframe>
```



Customizable parameter to be inserted as `query params` in `url` -

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `isWidget` | `string` | `true` **Required** |
| `widgetId` | `string` | WidgetId provied by business team. **Required** |
| `fromChain` | `string` | ChainId of source chain |
| `toChain` | `string` | ChainId of destination chain |
| `fromToken` | `string` | Address of source token |
| `toToken` | `string` | Address of destination token|

Router Widget with restiricted parameters - 
```html
  <iframe height="610px" width="420px" 
  src="https://app.routerprotocol.com/swap?isWidget=true&widgetId=widget-0101&fromChain=137&fromToken=0xc2132d05d31c914a87c6611c10748aeb04b58e8f&toChain=56&toToken=0x6855f7bb6287F94ddcC8915E37e73a3c9fEe5CF3&dstChains=137,56&dstTokens=0x6855f7bb6287F94ddcC8915E37e73a3c9fEe5CF3,0x980111ae1B84E50222C8843e3A7a038F36Fecd2b"
  style="border: none;border-radius: 11px;box-shadow: 3px 3px 10px 4px rgba(0, 0, 0, 0.05);">
  </iframe>
```



Optional restriction parameters to be used with the above customizable parameters inserted as `query params` in `url`-

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `srcChains` | `string` | ChainId of source chains seperated by comma that only needs to be shown in selection menu. |
| `dstChains` | `string` | ChainId of destination chains seperated by comma that only needs to be shown in selection menu. |
| `srcTokens` | `string` | Address of source tokens belonging to list of `srcChains` seperated by comma that only needs to be shown in selection menu.|
| `dstTokens` | `string` | Address of destination tokens belonging to list of `dstChains` seperated by comma that only needs to be shown in selection menu.|

Note - 
1. `height` and `width` are customizable but we recommend to keep the aspect ratio same.
2. If using restricted chain parameter then mention atleast one token belonging to each chain written in the restricted chain parameter.



