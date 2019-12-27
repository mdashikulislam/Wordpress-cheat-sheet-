//For language  
<?php language_attributes();?>

//For Character Set
<?php   bloginfo('charset');?>

//For Header and Footer calling in a file
header and footer file name must be header.php and footer.php
<?php get_header();?> //Calling Header File
<?php get_footer();?> //Calling Footer

//For Calling any file 
we can call any by file name but not use file extension 
<?php get_template_part('File Name')?>

// For Single Post show
