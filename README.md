# I18nNewbie

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 7.3.3.

## Steps:
Follow [here](https://alligator.io/angular/internationalization/)

1. Add `i18n` directive to mark text for translation
2. In `package.json`:
```
"script": {
  ...
  "int:extract": "ng xi18n"
}
```
Run `npm run int:extract`, it extracts all of messages (that have `i18n` attribute)
=> make in messages file out of that 
Result: File `messages.xlf` in source.
This is XML file.
3. In `package.json`:
```
"script": {
  ...
  "int:extract": "ng xi18n --output-path locale"
}
```
4. Go Translation in folder locale.
5. In `angular.json`:
```
"build": {
  ...
  "configurations": {
    ...
    "production": {
      "fr": {
        "aot": true,
        "outputPath": "dist/under-c-fr/",
        "i18nFile": "src/locale/messages.fr.xlf",
        "i18nFormat": "xlf",
        "i18nLocale": "fr",
        "i18nMissingTranslation": "error"
      }
    }
  }
},
"serve": {
  ...
  "configurations": {
    "production": {
      "browserTarget": "i18n-newbie:build:production"
    },
    "fr": {
      "browserTarget": "i18n-newbie:build:fr"
    }
  }
}
```
6. In `package.json`:
```
"script": {
  ...
  "start": "ng serve",
  "start:fr": "ng serve --configuration=fr",
  "build": "ng build",
  "build:fr": "ng build --configuration=fr",
  ...
  "int:extract": "ng xi18n --output-path locale"
}
```
7. Run `ng serve --configuration=fr`
## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).
