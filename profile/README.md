# Configuring your Sigma Gallery

## Table of contents
1. Introduction
    1. Configuring your SigmaGallery
    2. Validating your .yml file
2. Banner
3. Collections
    1. Editing the collections.yml file
    2. Editing the collection1.yml file

## Introduction

### Configuring your Sigma Gallery
Please note that it may take up to 5 minutes for changes made to the config files to be reflected on the website. It is important to follow the default syntax, as shown in the examples, when making changes. Failing to do so may result in incorrect data display on the page.

### Validating your .yml file
It is recommended to validate your edited .yml file using a YAML validator such as [codebeautify's yaml validator](https://codebeautify.org/yaml-validator) if you have made big changes. This will ensure that your configuration is valid and will work correctly.

## Banner
The banner will be displayed at the top of the page. You can enter a title, description, an image, mint addresses, and links using small buttons with icons.

```yaml
title: Title
description: Description
image: Link to image
mintAddresses:
  - MintAddress1
  - MintAddress2
bannerLinks:
  - label: Twitter
    url: https://twitter.com/
    icon: fa-brands fa-twitter fa-fw
  - label: Telegram
    url: https://t.me/
    icon: fa-brands fa-telegram fa-fw
  - label: Discord
    url: https://discord.com/users/
    icon: fa-brands fa-discord fa-fw
```

## Collections
You can display one or multiple collections. If only one collection is specified, no buttons will be displayed and the single collection will be loaded automatically.

To retrieve data about your NFTs, you can use the tool provided by Sigma Gallery. Simply perform a search by token name or issued address, then copy the results from the “Search Results” box and paste them into your collection YAML file.

**Editing the collections.yml file**
Define your collections in this file. The label field sets the button label for each collection. The data field specifies the filename(s) of your collection(s). The specified files contain the data for each collection.

```yaml
collections:
  - label: Collection 1
    data: collection1.yml
  - label: Collection 2
    data: collection2.yml
  - label: Collection 3
    data: collection3.yml
```

### Option 1: Displaying a collection using only tokenIds
If you only have the tokenIds for your NFTs, you can create a YAML file containing a list of tokenIds to display your collection. This file can be named as specified in collections.yml. In this example, we’ll use collection1.yml. For each NFT, set the tokenid. It’s recommended to add a label for easy identification, but this is optional. By default, the media linked to the NFT retrieved using the tokenid will be treated as an image. However, if you want to add a video NFT, you can do so by adding "format: video" to the corresponding entry.

The NFT’s title, description, and media (image or video) will automatically be fetched from the blockchain using the token ID. You can find the tokenID of your NFTs using ErgoTokens or be using Sigma Gallery's search tool.

```yaml
tokenids:
  - label: NFT #1
    tokenid: your_token_id_here
  - label: NFT #2
    tokenid: your_token_id_here
  - label: Video NFT Example
    tokenid: your_token_id_here
    format: video
```

### Option 2: Displaying a collection using full NFT data (Recommended)
If you have the full data for your NFTs, including their name, description, and media URL, you can create a YAML file containing this data to display your collection. This file can be named as specified in collections.yml. In this example, we’ll use collection1.yml. For each NFT, set the tokenId, name, description, and either imageUrl or videoUrl, depending on whether the NFT is an image or video.

You can use the tool provided by Sigma Gallery to search for your NFTs and retrieve their full data in YAML format. Simply perform a search by token name or issued address, then copy the results from the “Search Results” box and paste them into your collection YAML file.

Using this method your NFTs will be displayed instantly.

To ensure images are optimized in the correct format, if your collection contains gifs make sure you add "format: gif" below the imageUrl as shown in the example.

```yaml
nfts:
- tokenId: your_token_id_here
  name: 'NFT #1'
  description: 'Description of NFT #1'
  imageUrl: 'https://example.com/image1.jpg'
- tokenId: your_token_id_here
  name: 'NFT #2'
  description: 'Description of NFT #2'
  imageUrl: 'https://example.com/image2.gif'
  format: gif
```

### Using Sigma Gallery's NFT search

[NFT Search](https://sigma.gallery/nftsearch)

Search by token name: In the “Search by token name” section, enter a search query to find assets with the specified name. You can also enter an optional address and description to further filter the results. Check the “Hide burned” checkbox if you want to exclude burned assets from the results. Click the “Search” button to perform the search. The results will be displayed in the “Search Results” box below. You can copy the results to your clipboard by clicking the “Copy results” button.

Search by issued address: In the “Search by issued address” section, enter an address to find NFTs issued by that address. You can also enter an optional name and description to further filter the results. Check the “Hide burned” checkbox if you want to exclude burned NFTs from the results. Click the “Search” button to perform the search. The results will be displayed in the “Search Results” box below. You can copy the results to your clipboard by clicking the “Copy results” button.

Search NFT data: In the “Search NFT data” section, enter a list of tokenIds from one of the previous searches. Check the “Hide burned+” checkbox if you want to exclude NFTs that are in one of the known burn addresses (note that this check may be slow). Click the “Submit” button to retrieve data about your NFT collection. The data will be displayed in YAML format in the “Search Results” box below. You can copy the data to your clipboard by clicking the “Copy results” button, and then paste it into a YAML file to display your NFT collection.
