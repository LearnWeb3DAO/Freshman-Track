# Setting up a crypto wallet

In this module you will learn about what Crypto Wallets are and how to download one. 🤔

## Introduction

To understand crypto wallets fully, we have to understand some concepts about the blockchain, which will help us in understanding how a wallet aids us. Let's start off.

## What is an address? 🤨

An address is a string of text generated using cryptography to represent your account on the blockchain. This address can be shared publicly with others, and is completely safe to do so. You can send and receive funds from and to your wallet address. Basically, the address is your unique identifier on the blockchain and represents your 'account'. An example of an Ethereum address is: `0x01573Df433484fCBe6325a0c6E051Dc62Ab107D1`.

<Quiz questionId="3088223f-7ba3-4aee-9e75-c4a9dfee84e4" />

<Quiz questionId="12d7b8c0-59c7-4d3d-93f0-6dc7ede80d1d" />

## What are private keys? 🔐

A private key is the counterpart to an address. Each address has an associated private key. As the name suggests though, this is meant to be kept private and not shared with anyone.

You can think of it like a password, a really strong one, that contains a bunch of letters and numbers that allow you to prove ownership over your address. Anyone who has the private key has access to make transactions from your address i.e. send money from your address to theirs.

A private key looks something like this: `E9873D79C6D87DC0FB6A5778633389F4453213303DA61F20BD67FC233AA33262`

If you think of your address as a username for your account, the private key is its password. Therefore sharing your address is okay, but never ever share your private key or someone might steal your funds - and then nothing can be done about it.

<Quiz questionId="2f0f1c91-7171-4039-bc84-8d6efbb717ff" />

**Caution: Since blockchains are decentralized, there is no 'forgot password' option. If you lose your private key, you lose access to your account. Similarly, if someone steals your private key and steals your funds, you cannot do anything about it. It is VERY important to keep this private key safe.**

For developers, we often use the private key as part of our codebase to perform certain transactions, such as deploying our own smart contracts to the Ethereum network. While you are still learning, we highly suggest you use a separate account entirely for development than you use for storing any sort of funds. Unfortunately, beginner developers often use the same account they have funds on, and accidentally share their codebase publicly - and hackers can see your private key in the codebase and end up stealing funds. Please take that as a tale of caution.

<Quiz questionId="1d8fff7f-57ac-4555-ac2b-94c95c76f70d" />

## What is a seed phrase? 👮‍♀️

A seed phrase is like a master password - the password of passwords!

Think of a password manager, something like Lastpass or 1Password. These applications, within them, store your usernames and passwords for other apps securely, and themselves have a password. So, if someone hacks your password manager, they also get access to all accounts stored within it.

A crypto wallet is kind of like a password manager, where you can manage multiple blockchain accounts. If the private key is the password to a single account, the seed phrase is kind of like the master password for that wallet.

<Quiz questionId="530db4f0-937f-409f-ba7c-9456b0174151" />

When you create a new crypto wallet, you will be presented with a seed phrase you should absolutely securely store and back up. Any new accounts you generate from inside that wallet will all be linked to the seed phrase. That one seed phrase will always generate the same accounts, with the same private keys and addresses for each.

So for example if you created a wallet, and then created 5 accounts within it, your seed phrase manages all 5. If you wanted to switch to a new wallet, you could either import the 5 wallets individually - by using their individual private keys - or just import using the seed phrase, and it would regenerate the same 5 accounts.

An example of a seed phrase is: `dove lumber quote board young robust kit invite plastic regular skull history`

<Quiz questionId="d4eae61d-fcf7-4447-9dcd-0bd737a687ce" />

## What is a crypto wallet then? 😛

Crypto wallets are a manager for your accounts, and mainly their private keys. They also allow you to interact with decentralized applications, and allow connecting to a dApp through the wallet, acting as a single sign-on for all applications built on the blockchain.

At LearnWeb3 as well, you can go into the Dashboard and connect your crypto wallet (after you have set it up), which will let us know what your address is so we can send you some sick NFTs when you graduate from our tracks!

<Quiz questionId="6566fc7a-661a-4a6e-b426-d2f851f697f9" />

## Setting up a Wallet 🎉

### IMPORTANT 🛑

Make sure to create a new wallet for development purposes only. **Do NOT use your own wallet with live funds for any development purposes**. Throughout this course we'll be expecting you to use this newly created development wallet whenever we mention to include the wallet details or its private keys.

### Continuing 😎

For Ethereum, there are a number of wallet options available. The easiest to get started using, and most developer friendly, are either Metamask or Coinbase Wallet.

Both are Ethereum crypto wallets that can be installed as browser extensions, or as a mobile apps. You can find the download links below. We suggest downloading any one of them, and setting it up, before proceeding with the track.



- [Download Metamask](https://metamask.io/download.html)
- [Download Coinbase Wallet](https://www.coinbase.com/wallet)

<Quiz questionId="96c7e46e-5d73-420c-b9da-088f4ad2b29a" />

Other alternatives include Trust Wallet, Atomic Wallet, Rainbow Wallet, Frame.sh, etc.

- [Rainbow Wallet](https://rainbow.me/)
- [Trust Wallet](https://trustwallet.com/)
- [Atomic Wallet](https://atomicwallet.io/)
- [Frame.sh](https://frame.sh/)

<Quiz questionId="0941bbfc-0bbc-4897-ae15-0a4a87c71b16" />

<SubmitQuiz />
