Menu Export
==================

Drupal 7 module to export menus easily. Also provides an import function.

Export menu
-----------

1. Go to admin/structure/menu
2. Choose your menu to export (edit menu)
3. Click on "Export Menu" tab
4. Copy / Paste the code into a file
 
Import menu
-----------

An export file generated by this module creates an object `$menu`.

You can import this object with the function `menu_export_menu_import($menu)`

Example of awesome import
-------------------------

```php
  $filepath = drupal_get_path('module', 'my_module') . '/menus';
  $files = drupal_system_listing('/\.inc$/', $filepath, 'name', 0);

  foreach($files as $file) {
    include_once $filepath . "/" . $file->filename;
    menu_export_menu_import($menu);
  }
```

With that piece of code you will be able to import a bunch of menus : just put some **.inc** files into a directory called **menus** inside your module **my_module**.

![That's All Falks !](https://33.media.tumblr.com/tumblr_m7xpvp6wtZ1qarcjno1_500.gif "That's All Falks !")
