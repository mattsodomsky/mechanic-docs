# Theme object

##  How to access it

* Use `{{ theme }}` in tasks responding to shopify/themes events
* Look up specific themes by their ID, using `{{ shop.themes[12345678900] }}` 
* Loop through all themes: `{% for theme in shop.themes %}`

## What it contains

* [Every property from the Shopify API](https://shopify.dev/docs/admin-api/rest/reference/online-store/theme)
* An array of [asset objects](https://docs.usemechanic.com/article/456-the-theme-asset-object): `{{ theme.assets }}`
