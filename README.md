
## About
A Drupal recipe of type "Site" that configures a standard blogging site, leveraging core recipes, modules and themes,
and incorporating the Navigation module to provide a seamless editor experience.

### Usage

- Create drupal project by running below command.
  ```
  composer create-project drupal/recommended-project project && cd project
  ```
- Update your project composer.json `extra.installer-paths` for recipes.
  ```
   "extra": {
      "installer-paths": {
        ...
        "web/recipes/contrib/{$name}": [
            "type:drupal-recipe"
        ]
      }
      ...
   }
  ```
- Update project composer.json `repository` section to fetch this recipe from vcs.
  ```
  ...
  {
    "type": "vcs",
    "url": "git@github.com:chandu7929/blogging.git"
  }
  ```
- Add this recipe using composer.
  ```
  composer require drupal/blogging
  ```
- Site set up using this recipe by running below drush command.
  ```
  ./vendor/bin/drush si recipes/contrib/blogging --account-pass admin
  ```
- Visit your newly setup site using blogging recipe at [http://127.0.0.1:8888](http://127.0.0.1:8888) by running drush command `./vendor/bin/drush rs`
