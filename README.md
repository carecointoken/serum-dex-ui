# Serum DEX UI

An implementation of a UI for the Serum DEX.

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

### Running the UI

Run `yarn` to install dependencies, then run `yarn start` to start a development server or `yarn build` to create a production build that can be served by a static file server.

### Collect referral fees

If you are hosting a public UI using this codebase, you can collect referral fees when your users trade through your site.

To do so, set the `REACT_APP_USDT_REFERRAL_FEES_ADDRESS` and `REACT_APP_USDC_REFERRAL_FEES_ADDRESS` environment variables to the addresses of your USDT and USDC SPL token accounts.

You may want to put these in local environment files (e.g. `.env.development.local`, `.env.production.local`). See the [documentation](https://create-react-app.dev/docs/adding-custom-environment-variables) on environment variables for more information.

NOTE: remember to re-build your app before deploying for your referral addresses to be reflected.

---

See the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started) for other commands and options.

---

See [A technical introduction to the Serum DEX](https://projectserum.com/blog/serum-dex-introduction) to learn more about the Serum DEX.

See [serum-js](https://github.com/project-serum/serum-js) for DEX client-side code. Serum DEX UI uses this library.

See [sol-wallet-adapter](https://github.com/project-serum/sol-wallet-adapter) for an explanation of how the Serum DEX UI interacts with wallet services to sign and send requests to the Serum DEX.

See [spl-token-wallet](https://github.com/project-serum/spl-token-wallet) for an implementation of such a wallet, live at [sollet.io](https://sollet.io).
