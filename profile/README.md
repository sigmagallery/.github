# Configuring your Sigma Gallery

## Table of contents
1. Introduction
    1. Configuring your SigmaGallery
    2. Validating your .yml file
2. Editing the theme.yml file
    1. Available themes
3. Banner
4. Collections
    1. Editing the collections.yml file
    2. Editing the collection1.yml file
5. Optional
    1. Creating your own custom theme

## Introduction

### Configuring your Sigma Gallery
Please note that it may take up to 5 minutes for changes made to the config files to be reflected on the website. It is important to follow the default syntax, as shown in the examples, when making changes. Failing to do so may result in incorrect data display on the page.

### Validating your .yml file
It is recommended to validate your edited .yml file using a YAML validator such as [codebeautify's yaml validator](https://codebeautify.org/yaml-validator) if you have made big changes. This will ensure that your configuration is valid and will work correctly.

## Editing the theme.yml file
Select one of the provided themes and enter the information as demonstrated below.

```yaml
theme: dark
```
Visit the [Demo page](https://sigma.gallery/demo/themepreview/) and use the drop-down button in the top left corner to preview all available themes.

### Available themes:
```yaml
- autumn
- autumn-sunset
- city-lights
- crimson-red
- dark
- darkmode
- darkmode-blue
- darkmode-green
- darkmode-orange
- darkmode-pink
- darkmode-purple
- darkmode-red
- deep-blue
- deep-red
- desert-mirage
- earthy-brown
- forest-green
- lavender-fields
- light
- lightmode
- lightmode-blue
- lilac-dreams
- midnight-blue
- midnight-purple
- midnight-sky
- mint-breeze
- minty-fresh
- ocean-breeze
- purple-haze
- rainforest
- rustic-red
- spring
- spring-blossom
- summer
- summer-breeze
- sunset-boulevard
- teal-forest
- tropical-paradise
- twilight-blue
- vibrant-orange
- winter 
- winter-wonderland
```

## Banner
The banner will be displayed at the top of the website. You can enter a title, description, an image, mint addresses, and links using small buttons with icons.
It is recommended to use a square image for the banner. For example this could be one of your favorite NFTs.

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
You can display one or multiple collections.
In most cases, a separate page is recommended.
Use buttons to toggle between collections.
If only one collection is specified, no buttons will be displayed and the single collection will be loaded automatically.

### Editing the collections.yml file
Define your collections in this file.
The label field sets the button label for each collection.
The data field specifies the filename(s) of your collection(s).
The specified files contain the data for each collection

```yaml
collections:
  - label: Collection 1
    data: collection1.yml
  - label: Collection 2
    data: collection2.yml
  - label: Collection 3
    data: collection3.yml
```

### Editing the collection1.yml file
This file can be named as specified in collections.yml. In this example, we’ll use collection1.yml. For each NFT, set the tokenID. It’s recommended to add a label for easy identification, but this is optional. By default, the tokenID will be treated as an image NFT. However, if you want to add a video NFT, you can do so by adding `format: video` to the corresponding entry.

The NFT's title, description, and media (image or video) will automatically be fetched from the blockchain using the token ID. You can find the tokenID of your NFTs using [ErgoTokens](https://ergotokens.org).

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

## Optional

### Creating your own Custom Theme

1. Open your SigmaGallery in Firefox.
2. Right-click on the page and select "Inspect" to access the developer tools.
3. In the developer tools, select the "Style Editor" tab.
4. In the Style Editor, select the CSS file for your selected theme (e.g., `dark.css`).
5. You will see the CSS code for the selected theme, which includes variables for different colors such as `--header`, `--text`, `--background`, etc.
6. You can use a website such as [color-hex.com](https://www.color-hex.com/) or [coolors.co](https://coolors.co/) to see what each HEX color looks like and make changes to the values of the variables as desired. You can also use AI tools to generate a custom color palette for your theme.
7. Changes you make to the CSS file will be reflected on your page in real-time, but they will only be visible to you until you refresh the page.
8. If you are satisfied with your changes, copy all of the code from the Style Editor and paste it into the `style.css` file in your repository.
9. Your new custom theme will now load automatically when you visit your SigmaGallery.

By following these steps, you can easily edit your own theme and customize the appearance of your SigmaGallery using color palette generators or AI tools to create a unique look for your page.
