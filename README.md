####For language  
```php
<?php language_attributes();?>
```
####For Character Set
```php
<?php   bloginfo('charset');?>
```
####For Header and Footer calling in a file
header and footer file name must be [header.php] and [footer.php]
```php
<?php get_header();?> //Calling Header File
<?php get_footer();?> //Calling Footer
```
####For Calling any file 
we can call any by file name but not use file extension 
```php
<?php get_template_part('File_Name')?>
```
#### For Single Post show
File name must be [single.php]
