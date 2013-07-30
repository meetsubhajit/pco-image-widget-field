=== Pco Image Widget Field ===
Contributors: compute, jamesbonham
Tags: image, upload, widget
Requires at least: 3.5.0
Tested up to: 3.5.2
Stable tag: 1.0
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html

Add image widget fields to your custom build widgets.

== Description ==

= Features =
Pco Image Widget Field allows developers to add multiple image fields for their widgets.

By calling <code>pco_image_widget()</code> inside your widgets's form() function, you will be able to use give your users a way to add images with the Wordpress Media Frame.
Change the title and update text by adding ´array( 'title' => 'my title', 'update' => 'my-update-text' )´

= Translations =
English by [compute](http://profiles.wordpress.org/compute)
Danish by [compute](http://profiles.wordpress.org/compute)

There are just a few strings to translate. But great value to have more languages available.
Please [contact us](mailto:phh@peytz.dk) to add your translation to the plugin!

== Installation ==

1. Add the plugin by either downloading the folder and uploading it to the `wp-content/plugins` directory or install it from the Control Panel `Plugins->Add New`
1. Activate ´Pco Image Widget Field´ from the Plugins menu ´Plugins->Installed Plugins´
1. Put ´pco_image_field( $this, $instance );´ inside your Widget's Form() method.
1. It's possible to add settings to the function by adding a settings array for the third argument: array( 'title' => 'your-title', 'update' => 'your-update-text', 'field' => 'your-image-field' )
1. After that the field will appear inside your widget. If you want to add more fields you will have to change the field setting
1. Note that this plugin will not save your data or show your image anywhere except for inside the widget. It will simple store the field inside the $new_instance array and wait for you to save the giving image id.

== Frequently Asked Questions ==

= Will this work for Wordpress earlier than 3.5.0? =
No. This plugin was build to make the Media Frame more useful.
Older versions of Wordpress will have to use thickbox instead. You can use the [Widget Image Field](http://wordpress.org/plugins/widget-image-field/) plugin instead, but it's recommented to update your Wordpress install instead.

= Will this automatic add an image field for my widget? =

No. This plugin is only used for the building block.
You will have to manually add the function ´pco_image_field( $this, $instance )´ inside your widget.

= But I cannot code =
Sad. Try the alternatives instead: [Image Widget](http://wordpress.org/plugins/image-widget/) or [Simple Image Widget](http://wordpress.org/plugins/simple-image-widget/)

This plugins was build to let developers easily add an image field to their widgets.
If you have a developer available this will make an easy task.

= I have added the function but it return warnings and kills my script. Eh? =
Make sure the plugin has been activated. By adding a function that doesn't exists will produce a PHP warning and kills the script. To prevent these errors you can use a function_exists before calling ´pco_image_field()´

= What if I don't declare any fields to the settings array? =
You dont have to define the settings array. The default field is ´image_id´ and is recommended to use for simplicity.

= What if I want to create multiple image fields inside my widget? =
Define a field to the setting array. Example:
pco_image_field( $this, $instance, array( 'field' => 'my_image_id' ) );
pco_image_field( $this, $instance, array( 'field' => 'my_next_image_id' ) );
pco_image_field( $this, $instance, array( 'field' => 'my_last_image_id' ) );

= The image will not save =
Save your field inside your widgets ´update()´.

= None of my data is saved =
There is a problem with your widget.

= It seems like it's saving my data but I don't get anything on my frontend? =
Then you will have to output the image in your theme.
Get the image id from ´$instance['your-field']´ and use a function like ´wp get attachment image()´.

= Well your plugin conflicts with... =
Let us know!
Please, add a new ticket inside our support forum!

= Too much hard coding :( . I need a hook/functionality for... =
Please, add a new ticket inside our support forum and tell us about the feature request you need!

== Screenshots ==

1. Select your image.
2. Media frame opens. Pick your image and click update.
3. Save your stuff.
4. And output the image in your widget.

== Changelog ==

= 1.0 =
* First release
