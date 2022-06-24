---
sidebar_position: 2
---

# Integration guide

:::tip
Do you work at a **Bank**, **Financial Institution** or a **Cryptocurrency Exchange**? Its 
easy to integrate XRPScan in your application. We support deep links for
**Accounts**, **Transactions**, **Ledgers**, **Amendments** and **Validator nodes**.
All pages support desktop as well as mobile layouts.
:::

## Account

To link to an Account, use:

```
https://xrpscan.com/account/[ACCOUNT_ADDRESS]
```

`ACCOUNT_ADDRESS` in the XRP Ledger is identified by an address in the Base58
format. An [Account address](https://xrpl.org/basic-data-types.html#addresses)
has the following properties:

- A string of length between 25 to 35 characters. 
- Starts with the character `r`.
- Is case sensitive.
- Uses alphanumeric characters, excluding the number `0` capital letter 
  `O`, capital letter `I`, and lowercase letter `l`.

:::info Example
```bash
https://xrpscan.com/account/rGeyCsqc6vKXuyTGF39WJxmTRemoV3c97h
```
:::

## Transaction

To link to a Transaction, use::

```
https://xrpscan.com/tx/[TRANSACTION_HASH]
```

`TRANSACTION_HASH` in the XRP Ledger is identified by a 64 charcters long
string. A [Transaction hash](https://xrpl.org/basic-data-types.html#hashes) 
has the following properties:

- A string exactly 64 characters in length.
- Hex character set: `0-9` and `A-F`.
- Not case sensitive, but typically written in upper case letters.

:::info Example
```
https://xrpscan.com/tx/5A9E938DB7DA6193446A383898C7A66518E9FCE65DFFD82DF0B7E65844F3EB61
```
:::

## Ledger

To link to a Ledger, use::

```
https://xrpscan.com/ledger/[LEDGER_INDEX]
```

`LEDGER_INDEX` in the XRP Ledger is identified by a 32 bit unsigned integer.
A [Ledger index](https://xrpl.org/basic-data-types.html#ledger-index) 
has the following properties:

- A number between **32,570** and **4,294,967,295**.
- Must be less than the last closed ledger index.

:::info Example
```
https://xrpscan.com/ledger/44023993
```
:::

## Validator

To link to a Validator node, use::

```
https://xrpscan.com/validator/[VALIDATOR_PUBLIC_KEY]
```

`VALIDATOR_PUBLIC_KEY` in the XRP Ledger is identified by upto 53 charcters
long string in Base68 format. A [Validator public key](https://xrpl.org/base58-encodings.html)
has the following properties:

- A string in Base58, upto 53 characters in length.
- Starts with the character `n`, commonly followed by `H`.
- Is case sensitive.
- Uses alphanumeric characters, excluding the number `0` capital letter 
  `O`, capital letter `I`, and lowercase letter `l`.

:::info Example
```
https://xrpscan.com/validator/nHDB2PAPYqF86j9j3c6w1F1ZqwvQfiWcFShZ9Pokg9q4ohNDSkAz
```
:::

## Amendment

To link to an Amendment, use::

```
https://xrpscan.com/amendment/[AMENDMENT_ID]
```

`AMENDMENT_ID` in the XRP Ledger is identified by upto 64 charcters
long string. An [Amendment ID](https://xrpl.org/known-amendments.html)
has the following properties:

- A string exactly 64 characters in length.
- Hex character set: `0-9` and `A-F`.
- Case sensitive.

:::info Example
```
https://xrpscan.com/amendment/3C43D9A973AA4443EF3FC38E42DD306160FBFFDAB901CD8BAA15D09F2597EB87
```
:::