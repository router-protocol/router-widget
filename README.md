
# Router Widget

Code snippet given below to use router widget.


## Usage/Examples
Router Widget to be used as `iframe` given below - 
```html
<iframe
    height="610px"
    width="420px"
    src="http://app.routerprotocol.com/swap
        ?isWidget=true
        &fromChain=56
        &toChain=137
        &fromToken=0xe9e7CEA3DedcA5984780Bafc599bD69ADd087D56
        &toToken=0x16ECCfDbb4eE1A85A33f3A9B21175Cd7Ae753dB4"
    style="
        border: none;
        border-radius: 11px;
        box-shadow: 3px 3px 10px 4px rgba(0, 0, 0, 0.05);
    "
>
</iframe>
```



Customizable parameter to be inserted as `query params` in `url` -

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `isWidget` | `string` | `true` **Required** |
| `fromChain` | `string` | ChainId of source chain |
| `toChain` | `string` | ChainId of destination chain |
| `fromToken` | `string` | Address of source token |
| `toToken` | `string` | Address of destination token|

Note - `height` and `width` are customizable but we recomment to keep the aspect ratio same.



