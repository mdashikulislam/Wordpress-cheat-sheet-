#### For language  
```php
<?php language_attributes();?>
```
#### For Character Set
```php
<?php   bloginfo('charset');?>
```
#### For Header and Footer calling in a file
header and footer file name must be [header.php] and [footer.php]
```php
<?php get_header();?> //Calling Header File
<?php get_footer();?> //Calling Footer
```
#### For Calling any file 
we can call any by file name but not use file extension 
```php
<?php get_template_part('File_Name')?>
```
#### For Calling File from directory
```php
<?php echo get_template_directory_uri(); ?> /File name
```
#### For Post
```php
<?php if (have_posts()) : while (have_posts()):the_post();?>[Inside post Html Content] <?php endwhile;endif;?>// Post Fetch Loop
<?php the_permalink(); ?> //For hyperLink
<?php the_title();?> //For post title
 <?php the_excerpt();?> //For Post Body in short form
<?php the_time('M d, Y');?> //For Date and Time
<?php the_author();?> //For Author Name
<?php comments_popup_link('No Comment »','1 Comment »','% Comments »');?>//For comment Count
```

#### For Single Post show
File name must be [single.php]
