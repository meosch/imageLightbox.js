# imageLightbox.js for Drupal 8
This repository is just repackaging by changing the name of the repository and adding a composer.json file so it can be install on Drupal 8 with Composer.

## Install with composer for Drupal 8
[composer/installers](https://github.com/composer/installers) is already a requirement of a Drupal 8 web project. It allows custom installation paths for defined project types. Currently Drupal custom modules and themes are not a **type**, however it looks like this will change. I added [oomphinc/composer-installers-extender](https://github.com/oomphinc/composer-installers-extenderhttps://github.com/oomphinc/composer-installers-extender) so that I could add new types. For libraries add a new type of **drupal-library**. In the composer.json the extra section will look something like this:
```json
 "extra": {
        "installer-types": [
            "drupal-module-custom",
            "drupal-theme-custom",
            "drupal-library"
        ],
        "installer-paths": {
            "docroot/core": [
                "type:drupal-core"
            ],
            "docroot/modules/contrib/{$name}": [
                "type:drupal-module"
            ],
            "docroot/profiles/contrib/{$name}": [
                "type:drupal-profile"
            ],
            "docroot/themes/contrib/{$name}": [
                "type:drupal-theme"
            ],
            "drush/contrib/{$name}": [
                "type:drupal-drush"
            ],
            "docroot/modules/custom/{$name}": [
                "type:drupal-module-custom"
            ],
            "docroot/themes/custom/{$name}": [
                "type:drupal-theme-custom"
            ],
            "docroot/libraries/{$name}": [
                "type:drupal-library"
            ] 
        },
```
I have also added the project types of **drupal-theme-custom** and **drupal-module-custom** and installation paths for them. For more information on how to set this up see the documentation for the [oomphinc/composer-installers-extender](https://github.com/oomphinc/composer-installers-extenderhttps://github.com/oomphinc/composer-installers-extender) project.

Then add this Github repostitory as a repository in Composer and require the project.
```
composer config repositories.imagelightbox vcs https://github.com/meosch/imagelightbox
composer require meosch/imagelightbox
 ```
 <sub><sup>original documentation below</sup></sub>
 ---
 
# imageLightbox.js
A JavaScript plugin for touch-friendly image lightbox.

## Usage and Demo
Read [how to use it](https://osvaldas.info/image-lightbox-responsive-touch-friendly).
Check the [demo](https://osvaldas.info/examples/image-lightbox-responsive-touch-friendly).
