# Notes related to front-end development.

## Ionic
* Include font-awesome fonts in project.
    * [FontAwesome in Ionic](https://luiscabrera.site/tech/2017/01/09/fontawesome-in-ionic2.html)
        * Install FontAwesome - `npm install --save font-awesome`
        * Create script to copy fonts into `www/assets/fonts`

        * Set path to fonts in SCSS - `$fa-font-path: /assets/fonts;` in `scr/app/app.scss`; 
        * https://forum.ionicframework.com/t/adding-font-awesome-to-rc0/65925/3 - comments for using with sass to convert to ion-icon.

## rxjs
* Getting it to work with typescript
    * Error: `Uncaught TypeError: Cannot read property 'Observable' of undefined`. Works in plain javascript.
    * Fix:
        * Install type definitions for rxjs `npm install --save-dev @type/rx`
        * Import as `import * as Rx from 'rxjs'`