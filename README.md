## Adding your coin to Kermit DEX
For getting your token listed with a chart on the KermitX API, there is a one time fee of **1000 KERMIT tokens**.

To add your coin to Kermit Dex you will need to edit three files-

 1. [token-mints.json](https://github.com/KermitSwap/serum-dex-ui/blob/master/src/token-mints.json)
	 
	 After the last entry, add your own coin using this format
```json
...
,
 {
   "address":  "your token mint address",
   "name": " your ticker"
 }
]	
```
	
2. [markets.json](https://github.com/KermitSwap/serum-dex-ui/blob/master/src/markets.json)
		 
After the last entry, add your own coin using this format
	
```json
...
,
{
  "name": "your ticker/your stable coin pair",
  "address": "your market address",
  "deprecated": false,
  "programId": "9xQeWvG816bUx9EPjHmaT23yvVM2ZWbrrpZb9PusVFin"
 }
]	
``` 
	
3. [index.ts](https://github.com/KermitSwap/serum-history/blob/main/src/index.ts)
		 
Search for `const  nativeMarketsV3:` in the file. Add your coin at the end of the list.

```json
 "NINJA/USDC":"88HrMUm3RtXGF2F4Ftnb7P9Fdh2yz9qfmAgp7jh2CFs9",
 "TGT/USDC":"GfokD5aka4n8kqCgRiJtMYi4Xd1ZLBatkynxFGyKdNTc",
 "your ticker/your stable coin pair": "your market address",
``` 
	
After doing the steps above, fill this [form](https://forms.gle/9Xz99nXNdLc5xfUA6).
