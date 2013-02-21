Annotator Store for Habari
===============

This plugin adds a backend [store] for the [Annotator] annotation system to your site or application built with [Habari]. Approximately half of the API calls are currently supported. We have plans to bring the other API endpoints online as soon as possible. Currently the store is focused on creating and retrievng annotations.

[Annotator]: https://github.com/okfn/annotator/
[store]: https://github.com/okfn/annotator/wiki/Storage
[Habari]: https://github.com/habari
Usage
-----

The plugin is made up of a custom content type (annotation) and the plugin itself. To install, simply drop `annotation.php` and `annotations.php` into your `user/classes/` directory, and copy the plugin to your plugin directory. Once you activate the plugin, it will create the tables you need and the custom content type.

API
-----

This plugin uses the new Rest API system in Habari. Once activated the following endpoints are avaiable:

API Endpoint                                   | Description
---------------------------------------------- | -----------
`/v1/read/annotations`  		               | Called when a page is loaded that the annotator has been attached to. Returns a JSON object containing all the annotations for this page.
`/v1/create/annotation`			               | Annotator passes json to this method to create a given annotation.

Object Methods
-----

Annotations are created and retrieved as any object in Habari, by calling the appropriate static method on the object:

Methods		                                   | Description
---------------------------------------------- | -----------
`Annotation::get()`				               | Accepts the normal range of presets for any object in Habari (title, slug, pubdate, etc) as well as the custom fields defined in `filter_posts_get_paramarray()` in the annotation plugin.
`Annotations::get()`			               | Accepts the normal range of presets for any object in Habari (title, slug, pubdate, etc) as well as the custom fields defined in `filter_posts_get_paramarray()` in the annotation plugin.
`Annotation::create()`			               | Accepts the normal range of presets for any object in Habari (title, slug, pubdate, etc) as well as the custom fields defined in `filter_posts_get_paramarray()` in the annotation plugin.
`Annotations::delete()`			               | Accepts the normal range of presets for any object in Habari (title, slug, pubdate, etc) as well as the custom fields defined in `filter_posts_get_paramarray()` in the annotation plugin.
