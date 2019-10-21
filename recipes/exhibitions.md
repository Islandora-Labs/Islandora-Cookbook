# Exhibitions and TimeLine JS 

## Why Do We Need an Exhibitions Module?
Exhibits, unlike digital collections, expect to guide a user through the material in a particular linear order. This order is often not the same as the alphabetic or date order used to programmatically organize a digital collection of related materials. Exhibits also generally require the ability to tell a story about the resource nodes, to organize the resource nodes into subtopics, and to visually display the connections between the objects. TimelineJS, from KnightLabs, is an open-source tool that enables anyone to build visually rich, interactive timelines.

We are also hoping to create the ability for curators to create their own exhibits, using flags or groups, so that they can reuse the objects already in Islandora for digital scholarship without having to download and re-upload those objects, to aid in keeping the exhibits and master files in synch and aid in digital preservation.

## Installation

Download the module and enable it. By default, there are no library files to download because they are served from the NU Knight Lab CDN.
* Drupal 8 Module: [Views TimelineJS](https://www.drupal.org/docs/8/modules/views-timelinejs)

### Installation Steps
* `composer require 'drupal/views_timelinejs:^3.1'`
* `drush en views_timelinejs`
* `cd /var/www/html/drupal/web/libraries`
* `git clone --branch master https://github.com/NUKnightLab/TimelineJS3.git`

### Create the TimeLineJS
* Add a view and add desired filters
* Create taxonomy term (for example: “MyCollection”) and change the display within views to “TimelineJS”.
* **Problem:** Tweaks may be required to metadata fields for ordering/use in TimelineJS
* **Drupal 8 TimelineJS Module** already existed and can be demoed
* **Example:** 
![20191011-0014](https://user-images.githubusercontent.com/3343583/66680886-5d50ce80-ec26-11e9-84c4-c9b9f4ede175.png)

### Create the exhibit collection (with optional sub-collections)
* Create a collection, with optional sub-collections, to create an exhibition experience with one or more narrative stories.
* **Possible Drupal 8 Module solution:** [Flag Lists](https://www.drupal.org/docs/8/modules/flag-lists) looks promising, but configuration would require some more time  
* **Example:**
![20191011-0009](https://user-images.githubusercontent.com/3343583/66677402-650c7500-ec1e-11e9-8bdf-b5d5ad9c1975.png)

### Populate the Exhibit Collection and Exhibit Sub-Collections
* Select the resource nodes that will belong to the collection or sub-collection.
* **Possible solution:** Flag module looks promising, but it isn’t playing well with Flag Lists
* **Problem:** The Group module looks promising, but there isn’t adequate documentation for quick implementation
* **Example:** Flag the node
![20191011-0012](https://user-images.githubusercontent.com/3343583/66677507-9dac4e80-ec1e-11e9-8827-9ac77bcb4301.png)

* **Example:** Unflag it
![20191011-0013](https://user-images.githubusercontent.com/3343583/66677544-b87ec300-ec1e-11e9-9051-13f2ebff5fee.png)

* **Example:** Show the Curated List of Flagged Exhibition Resource Nodes
<img width="794" alt="Screen Shot 2019-10-11 at 1 05 53 PM" src="https://user-images.githubusercontent.com/3343583/66681691-1663d880-ec28-11e9-8aaf-46424aa1461b.png">

### Resource Node Media and Metadata
* Module should allow the choice of using the whole resource node (with metadata) or just the media

### Design Pages for Collection(s)
* Design collection pages with the provided rich text editor.
* Pages can contain headings, ordered lists, links, and more.
* Pages can describe a collection of exhibit collections, an exhibit sub-collection, or an individual resource node.
* **Current solution:** Embed file via type-ahead interface into Drupal page with web text editor.
* **Example:**
![20191011-0011](https://user-images.githubusercontent.com/3343583/66677586-cd5b5680-ec1e-11e9-944b-0cf03b13d921.png)


### Order Your Collection(s) (Optional)
* Customize whether or not the resource nodes or exhibits collections within the main exhibit collection are ordered and how they are ordered
* Default to be ordered with a “Last” and “Next” button on each object
* Choosing non-ordered changes the “Next” button on the last ordered sub-collection to a “Back to [Parent Collection Name]” button
**Problem:** There must be ways to order views with weights or other arbitrarily assigned values, but we didn’t immediately discover those.
* **Current solution:** With TimelineJS we currently have the ability to order by date.
* **Current solution:** With Views we can sort by any existing metadata field.
* **Possible solution:** When we create the pages that describe the resource nodes and exhibit collections, we can add a metadata field for weight. There already exists an interface for drag and drop.
* **Example:**
![20191011-0010](https://user-images.githubusercontent.com/3343583/66677636-e49a4400-ec1e-11e9-96cf-4f38239ef6bd.png)


### Permissions for Collections and Pages
* Permissions to edit the collections and pages must be sufficiently flexible (and granular) to allow a designated curator (faculty, staff or student) with the ability to assign a collection, sub-collection, or individual page to one or more individuals. This enables the curator to independently create a collection (of resource nodes) or to create the digital exhibition collaboratively by involving a group of people. Thus, faculty, staff and/or students might be able to collaboratively nest their independent exhibits within a larger exhibition.
* This process ensures that curators may **only edit** the pages in which the media or resource nodes are displayed, and **may not edit** the actual metadata of the resource node.
* Ideally, there will be the ability for the designated curator of the exhibit to “proof” the data in the collections, sub-collections, and nodes, before they go live
* Resource node-level permissions should include the ability to see metadata for the resource node (even if it isn’t going to be displayed as part of the exhibit)
* **Problem:** This use case is an extension of our original use case and we don’t have any recommendations of where to start looking for a solution.

### Contributors
* Mark Jordan
* David Keiser-Clark
* Don Richards
* Lucas van Schaik
* Alan Stanley
* Charlie Tillay
