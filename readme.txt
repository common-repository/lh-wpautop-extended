=== Plugin Name ===
Contributors: luehrsen
Tags: wpautop, developer
Donate link: https://flattr.com/profile/krautgamer
Requires at least: 3.0
Tested up to: 3.5
Stable tag: 1.0
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html

A small extension to the current wpautop function for the occasional need to prevent a certain HTML tags to be wrapped in paragraphs.

== Description ==

This plugin basically just consists of one function, that extends the functionality of Wordpress own wpautop function.

On several occasions a theme developer might feel the need, that a certain HTML Tag should not be wrapped in paragraphs. 
This plugin deactivates the standard wpautop function and replaces it with an extended version of that plugin. Upon 
activation of this plugin you'll have access to the 'lh_wpautop_block_elements' filter, which gives you the ability to extend,
modify and enhance the array of standard elements, which are per default not wrapped in `<p>` tags.

With that plugin you could place this function into the theme functions.php, Images and Iframes will no longer be wrapped in paragraphs.

`<?php 
function add_block_elements($block_elements){
        $block_elements[] = "iframe";
        $block_elements[] = "img";

        return $block_elements;
}
add_filter("wpautop_block_elements", add_block_elements);
?>`

This Plugin is brought to you by [Luehrsen // Heinrich](http://www.luehrsen-heinrich.de)

== Installation ==

1. Upload the plugin to the `/wp-content/plugins/` directory
2. Activate the plugin through the 'Plugins' menu in WordPress
3. You now have the filter 'wpautop_block_elements' available

== Frequently Asked Questions ==

= What is a filter? =

You should probably not use this plugin. But for further education I recommend to read the [WordPress Codex page on filters.](http://codex.wordpress.org/Plugin_API/Filter_Reference)

= What is the recommended usage for this plugin? =

If I were you, I would adopt this function into my theme for easier shipment. But always consider the risk of overwriting a potential newer, better and updated version of wpautop. If you do adopt this function, be sure to check the original wpautop function upon every Wordpress release and keep the function up to date.

= Wouldn't it be awesome to have this function built into Wordpress itself? =

Yes, indeed. That's why [I opened a ticket, that has this goal](http://core.trac.wordpress.org/ticket/23135).

= But Nacin is right by neglecting this change, isn't he? =

By saying "This mangling should not be left to plugins." he is probably right in terms of standards and regulations. But I've seen enough occasions of this functionality being a necessity, that's why I'm lobbying to implement it into WP Core. But it still is a tricky issue, where you should know, what you're doing.


== Changelog ==

= 1.0 =
* Initial release