# Mobile Wallet

On this page, we get you up and running with UNiD SDK, so that it will build a wallet which provides storage of cryptographic keys, credentials, and secrets on a mobile device. At the moment, we support React Native SDK.

## React Native

UNiD React Native SDK offers easy-to-use javascript modules for embedding identity wallet capabilities such as DID operations, VC operations, and DID communications through the underlying UNiD Core APIs and Drivers.

**Prerequisites**

Before we begin, make sure you have the following installed:

* `Node.js v10.x or later`
* `npm v6.13.x or later`

If you don't already have an account and UNiD tenant established, head over to [here](https://docs.getunid.io), then return to this page.

## Install

Add the `@unid/react-native-sdk` dependency:

```bash
npm install --save @unid/react-native-sdk
```

## Linking

Since our SDKs also support a local authentication and key management at OS native layer, we need to link the SDK to your native projects.

Above `react-native >= 0.60` you need to do:

```bash
npx @unid/wizard -i reactNative -p ios

cd ios
pod install
```

Since React Native SDKs support `auto-linking` and iOS relies on CocoaPods, you need to install dependencies. If you are running a project with `react-native < 0.60` you still need to call `react-native link`.

```bash
react-native link @unid/react-native-sdk
```

The link step or the `unid-wizard` call with patch your project accordingly. The UNiD Wizard will guide you through the process of setting everything up correctly. This has to be done only once, and the files created can go into your version control system.

The following changes will be performed:

* add the unid-cocoa package for native local authentication and key management on iOS
* configure UNiD for the supplied DSN in your _**index.js/App.js**_ files
* store build credentials in _**ios/unid.properties**_.

## Configure

After you've completed setting up a tenant and a wallet application in UNiD, UNiD will give you values: `client_id` and `client_secret`. These values are used for authorization when the wallet communicates with relying parties and SDS endpoints.

```javascript
import { Unid } from "@unid/react-native-sdk";

Unid.init({
    client_id: "client_id_token",
    client_secret: "client_secret_token",
    env_network: "testnet"
});
```

Great! Now that you've completed setting up React Native SDK. You can step forward to [Generate New DID](https://github.com/getunid/unid-docs/tree/a0e3cb7501479628b5df9b10630e3f29c181f7b2/wallet/1-did-operation/README.md).

