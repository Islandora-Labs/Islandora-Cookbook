# Islandora-Cookbook

## Introduction

In the spirit of [Islandora Awesome](https://github.com/Islandora-Labs/islandora_awesome), Islandora Cookbook is a curated list of great modules and other tools for Islandora 8. Because Islandora 8 is more tightly integrated with Drupal, most of these 'recipes' require only Drupal modules as ingredients.

We offer this list for discovery, but do not officially provide support for any of these modules. 

## Table of Contents

  * [Recipes](#recipes)
  * [Ingredients](#ingredients)
      * [Access Control](#access-control)
      * [Displays](#displays)
      * [Ingest](#ingest)
      * [Search](#search)
      * [Other](#other)

## Contribute

If you would like to contribute to this list, please check out [CONTRIBUTING.md](CONTRIBUTING.md).

If making a new entry, please ensure your pull request adheres to the following guidelines:

* Use the following format for new **ingredients**:
   * Ingredient Title (brief description to the problem solved or feature added) 
   * Make an individual pull request for each new item.
   * Link additions should be inserted alphabetically to the relavant category
   * New categories or improvements to the existing categorization are welcome.
   * Check your spelling and grammar.
   * The pull request and commit should have a useful title.

* Use the following format for new **recipes**:
   * Use the [recipe template](/recipes/recipe_template.md) as a guide.
   Recipe Title (brief description to the problem solved or feature added) 
     * List of required modules/libraries/software (with live links whereever possible) in the format `[Module Name](link)` 
     * Step-by-step instructions on how to deploy the listed module to accomplish the stated goal. More detail is better but short recipes are accepted as starters. Screenshots are ideal!
   * Make an individual pull request for each new item.
   * Create your recipe as a new .md file in /recipes
   * Add a link to your recipe in readme.md
       * Link additions should be inserted alphabetically to the relavant category
       * New categories or improvements to the existing categorization are welcome.
   * Check your spelling and grammar.
   * The pull request and commit should have a useful title.

If updating an existing entry:

* New categories or improvements to the existing categorization are welcome.
* Check your spelling and grammar.
* The pull request and commit should have a useful title.


## Troubleshooting/Issues

Having problems or solved a problem? Check out the Islandora google groups for a solution.

* [Islandora Group](https://groups.google.com/forum/?hl=en&fromgroups#!forum/islandora)
* [Islandora Dev Group](https://groups.google.com/forum/?hl=en&fromgroups#!forum/islandora-dev)

## Maintainers/Sponsors

Current maintainers:

* [Melissa Anez](https://github.com/manez)

## License

[![CC0](http://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, the owner has waived all copyright and related or neighboring rights to this work.

# Recipes

- [Collection Searching](./recipes/collection_search.md) - 
This recipe provides instructions how to configure a shallow or deep search in a specific collection.
- [Exhibitions and TimeLine JS](https://github.com/manez/Islandora-Cookbook/blob/master/recipes/exhibitions.md) - This recipe outlines how to build exhibits in Islandora 8, including the deployment of TimeLineJS.

# Ingredients

Below are modules and tools that might be useful to solve common use cases, presented without specific recipes.

## Islandora 8 Contributed Modules

Warning! - All modules are under development.

* [Basic Ingest](https://github.com/discoverygarden/basic_ingest) - Basic repository item ingest improvements.
* [Islandora RipRap](https://github.com/mjordan/islandora_riprap) - Fixity auditing 
* Islandora Repository Reports(https://github.com/mjordan/islandora_repository_reports) - Graphical reports on various aspects of an Islandora repository.
* [Islandora Bagger](https://github.com/mjordan/islandora_bagger) - Utility to generate Bags for objects using Islandora's REST interface using either a command-line tool or via a batch-oriented queue. 
* [Islandora Whole Object](https://github.com/mjordan/islandora_whole_object) - Islandora 8 module that provides some Drupal blocks containing various representations of an Islandora object.
* [Islandora RDM](https://github.com/roblib/islandora_rdm)

## Access Control

### Access Control By Taxonomy Tags

[Permissons by Term](https://www.drupal.org/project/permissions_by_term)

By default, Drupal allows you only to restrict access to Drupal nodes by coupling node content types to user roles. The Permissions by Term module extends Drupal by functionality for restricting view and edit access to single nodes via taxonomy terms. Since Islandora 8 objects can have taxonomy terms, this can be used to control access at the node and collection level. The submodule Permissions by Entity extends this control to the media level.

### Set a Date and Time for Publication

[Moderation Scheduler](https://www.drupal.org/project/moderation_scheduler)

Moderation Scheduler gives content editors the ability to schedule Islanodra nodes to be published at specified dates and times in the future. Can be combined with [Views Bulk Edit](https://www.drupal.org/project/views_bulk_edit) to set the same schedued publication date/time on multiple nodes at once.

## Displays

### Image Slideshow

[Views Slideshow](https://www.drupal.org/project/views_slideshow)

Views Slideshow can be used to create a slideshow of any content (not just images) that can appear in a View. Powered by jQuery, it is heavily customizable: you may choose slideshow settings for each View you create. It can be used to create an easy, adjustable slideshow of images from an Islandora 8 repository. Views Slideshow can be seen in action with Islandora objects on the front page [here](http://future.islandora.ca/)

## Ingest

### Batch Upload with a CSV

[Migrate Islandora CSV](https://github.com/Islandora-CLAW/migrate_islandora_csv)

This repository is a tutorial that will introduce you to using the Drupal 8 Migrate tools to create Islandora 8 content. Whether you will eventually use CSVs or other sources (such as XML or directly from a 7.x Islandora) this tutorial should be useful as it covers the basics and mechanics of migration.

This repository is also a Drupal Feature that, when enabled as a module, will create three example migrations ready for you to use with the Migrate API. 


## Search

### Custom Search Weighting

[Search Overrides](https://www.drupal.org/project/search_overrides)

This module provides a method for users with the necessary permissions to manually override the results being returned by Search API Solr. They will be able to choose a specific search term, and pick which nodes should be at the top, and also choose to exclude nodes so they will not be shown in the results. Currently only nodes are supported.

## Other

### Batch Editing

[Views Bulk Edit](https://www.drupal.org/project/views_bulk_edit)

A powerful tool that turns Views into a means of batch editing nodes, including Islandora repository objects. Once installled, create a view, add the fields that you would like to edit, add a `Views bulk operations (Edit)` field to the view, and select which actions you would like ot have available. The `Modify field values` action will allow you to batch edit the value for the same field across multiple objects. A demonstration of a simple bulk-editing view with a few fields and actions can be found [here](http://future.islandora.ca/islandora-batch-edit)

### Clone a Content Type

[Content Type Clone](https://www.drupal.org/project/content_type_clone)

A tool that allows you to clone an exsiting content type. Can be used to copy and easily make your own version of the Repository Item Content Type with fewer or edited fields, without starting over. Has options to also copy all nodes from the old type to the new, and to delete from the old type when copying.

### Gather User Feedback

[Content Feedback](https://www.drupal.org/project/content_feedback)

The Content Feedback module allows users and visitors to quickly send feedback messages about the currently displayed content, and can be applied to Islandora nodes. All content feedback messages are listed and grouped by status in an administrative feedback list.

### Send Your Content to Archive.org

[Wayback Submit to Archive.org](https://www.drupal.org/project/wayback_submit_archive)

A tool for automatically submitting the contents of your site to Archive.org. The Wayback Submit module will submit all node types on schedule, according to criteria set by the site admin (only certain node types, only certain views, etc).
