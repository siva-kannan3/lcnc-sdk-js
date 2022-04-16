# _Kissflow Low-code JavaScript SDK_

The JavaScript Software Development Kit (SDK) for Kissflow Low-code includes all the supported functions and code snippets that you can incorporate into your application while integrating with other services.

### 1) Get context
This function retrieves your account and application's context information, such as the **account ID** and **application ID**.
```js
kf.getContext().then((ctx) => {...})
// or
let ctx = kf.getContext()
/*
fetches contextual information, such as: 
ctx = {
  app: {_id },
  account: { _id }
}
*/
```
---

### 2) Get API via Kissflow Low-code SDK

This function lets you retrieve any external or Kissflow APIs. To access an internal Kissflow API, use an absolute URL, **(i.e., https://{your_sub_domain}.kissflow.com/user/2/{account_id})**. The Access key secret must be passed in the header. Refer **[Access keys](https://helpdocs.kissflow.com/user-settings/api-keys#access_keys)** to know how to locate your Kissflow API key and secret. Refer the developer guide to know more about our **[APIs](https://developers.kissflow.com)**.
> Note: The API call timeout for this method is 10 seconds.
```js
kf.api(url, config).then((res) => {...})
// or
let resp = await kf.api(url, config)
```
---

### 3) Formatter functions
##### Convert to Kissflow date format
This function lets you transform your date into Kissflow's date format. By default this conversion is based on the account timezone. If you want to customize the function for your timezone, you can optionally pass timeZone as second parameter to the function. Refer this [timezone list](https://github.com/siva-kannan3/lcnc-sdk-js/blob/readme/TIMEZONE.md#supported-timezone-list).
```js
kf.formatter.toDate("08-24-2021").then((res) => {...})
kf.formatter.toDate("08-24-2021",CUSTOM_TIMEZONE_ID).then((res) => {...})
// or
let value = kf.formatter.toDate("08-24-2021");
let value = kf.formatter.toDate("08-24-2021",CUSTOM_TIMEZONE_ID);
```
##### Convert to Kissflow DateTime format
This function lets you transform your date and time into Kissflow's DateTime format. By default this conversion is based on the account timezone. If you want to customize the function for your timezone, you can optionally pass timeZone as second parameter to the function. Refer this [timezone list](https://github.com/siva-kannan3/lcnc-sdk-js/blob/readme/TIMEZONE.md#supported-timezone-list).

```js
kf.formatter.toDateTime("2021-08-26T14:30").then((res) => {...})
kf.formatter.toDateTime("2021-08-26T14:30",CUSTOM_TIMEZONE_ID).then((res) => {...})
// or
let value = kf.formatter.toDateTime("2021-08-26T14:30");
let value = kf.formatter.toDateTime("2021-08-26T14:30",CUSTOM_TIMEZONE_ID);
```
##### Convert to Kissflow number format
This function lets you transform your number into Kissflow's number format. This conversion is based on locale. By default the CUSTOM_LOCALE points to "en-US" locale. If you want to customize the locale, refer this [table](https://www.npmjs.com/package/locale-codes#locale-list) and get the respective Tag for your locale.
```js
kf.formatter.toNumber("1,00,000.500000",CUSTOM_LOCALE).then((res) => {...})
// or
let value = kf.formatter.toNumber("1,00,000.500000",CUSTOM_LOCALE);
```
##### Convert to Kissflow currency format
This function lets you transform your current values into Kissflow's currency format. 
This conversion is based on locale. By default the CUSTOM_LOCALE points to "en-US" locale. If you want to customize the locale, refer this [table](https://www.npmjs.com/package/locale-codes#locale-list) and get the respective Tag for your locale.
```js
kf.formatter.toCurrency("1,00,000.500000", "USD",CUSTOM_LOCALE).then((res) => {...})
// or
let value = kf.formatter.toCurrency("1,00,000.500000", "USD",CUSTOM_LOCALE);
```
##### Convert to boolean
This function converts your value to a boolean value.
```js
kf.formatter.toBoolean("yes").then((res) => {...})
// or
let value = kf.formatter.toBoolean("yes");
```
##### Other supported boolean values
```js
let value = kf.formatter.toBoolean("1");
let value = kf.formatter.toBoolean("true");
let value = kf.formatter.toBoolean("no");
let value = kf.formatter.toBoolean("0");
let value = kf.formatter.toBoolean("false");
```
---
