# Configuring your Sigma Gallery

## Table of contents
1. Introduction
    1. Configuring your SigmaGallery
    2. Validating your .yml file
2. Editing the theme.yml file
    1. Available themes
3. Editing the data.yml file
    1. Optional: Uploading your logo to Github
4. Editing the links.yml file
    1. Adding and removing links
    2. Selecting icons from Font Awesome 6
5. Banner
6. Collections
    1. Editing the collections.yml file
    2. Editing the collection1.yml file
7. Optional
    1. Adding a favicon to your page
    2. Editing the style.css file
    3. Creating your own custom theme

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


## Editing the data.yml file
```yaml
pageTitle: Your Project's Name
pageDescription: Short description about your project for search engines
```
The page title will be inserted following the text "Sigma Gallery - ".

### Optional: Uploading your logo to Github
Here’s how you can upload an image to the repository and then get a direct URL to the image.

1. First, navigate to the repository where you want to upload the image.
2. Click on the Add file button and select Upload files. <br />
3. Drag and drop the image file or click choose your files to select the image from your computer. <br />
4. Enter a commit message and choose which branch you want to commit the changes to. Select the main branch. <br />
5. Click on Commit changes to upload the image to the repository. <br />

Once the image is uploaded, you can get a direct link to it by navigating to the image file in the repository. Right click the image and open it in a new tab. The raw.githubusercontent.com URL in the address bar can be used in the 'data.yml' to display your logo.

## Editing the links.yml file
```yaml
links:
  - label: Twitter
    url: https://twitter.com/my_username
    icon: fa-brands fa-twitter fa-fw
  - label: Telegram
    url: https://t.me/my_username
    icon: fa-brands fa-telegram fa-fw
  - label: Discord
    url: https://discord.com/users/my_user_id
    icon: fa-brands fa-discord fa-fw
  - label: Skyharbor
    url: https://www.skyharbor.io/my_profile
    icon: fa-solid fa-sailboat fa-fw
  - label: Auction House
    url: https://ergoauctions.org/my_auctions
    icon: fa-solid fa-brush fa-fw
```
### Adding and removing links
The links added here will be displayed in the navigation menu. You have the option to add or remove links as desired. Please ensure that the correct syntax is used when making changes.

### Icons
You may select any icon from Font Awesome 6 by visiting their [website](https://fontawesome.com/icons). Once you have chosen an icon, a code snippet will be displayed in the following format:

```html
<i class="fa-solid fa-file"></i>
```

Copy the class name, in this example “fa-solid fa-file”, and paste it into the icon field in the links.json file as demonstrated in the example above.
It is recommended to add "fa-fw" to the class. This will make sure the icons are equal in width.

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

### Adding a favicon to your page
To add a favicon to your page, generate one from an image using a tool such as [realfavicongenerator](https://realfavicongenerator.net/). Then, upload the resulting “favicon.ico” file to the main repository. It is important to name the file exactly ‘favicon.ico’, otherwise the icon will not load.

### Editing the style.css file
If you want to further change the appearance of your Sigma Gallery, you can do so by editing the style.css file in the main repository. This file can adjust the style of your page. This is completely optional and only recommended if you know the basics of CSS.

For example, here is the default CSS code that controls the size of the logo:

```css
/* Logo */
.logo-text  {
  font-size: 30px;
}
```
You can experiment with different values to find a style that you like. Once you have made your changes, save the style.css file and refresh your Sigma Gallery page with CTRL + F5 to see the updated style. It may take a few minutes before changes are reflected.

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
