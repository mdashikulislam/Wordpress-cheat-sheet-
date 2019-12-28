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
<?php echo  esc_url(home_url('/'));?> //For home Url
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
#### For Nav Menu Register and Connect
for nav menu register you need [functions.php] file and inside function define

for showing menu 
 ```php
    <?php
        wp_nav_menu(
            array(
                'theme_location' => '[menu  name]',
                'container_class'=>'[menu class name]',
                'items_wrap'=>'<ul class="[ul class name if exist]">%3$s</ul>'
            )
        );
    ?>
```
#### For Post
```php
<?php if (have_posts()) : while (have_posts()):the_post();?>[Inside post Html Content] <?php endwhile;endif;?>// Post Fetch Loop
<?php the_permalink(); ?> //For hyperLink
<?php the_title();?> //For post title
<?php the_content();?> //For post body in long form
 <?php the_excerpt();?> //For Post Body in short form
<?php the_time('M d, Y');?> //For Date and Time
<?php the_author();?> //For Author Name
<?php comments_popup_link('No Comment »','1 Comment »','% Comments »');?>//For comment Count
<?php the_post_thumbnail('thumb_name',array('class'=>'class_name'))?> //Calling post Thumb
```

#### For Single Post show
File name must be [single.php]
#### For Search
File name must be [search.php]
```html
    <form action="<?php echo esc_url(home_url('/'));?>" method="post"> 
        <input type="search" name="s"> <!---type must be [search] and name must be [s]--->
    </form>
```
#### For Category
File name must be [category.php]
```html
    <?php
        $args = array(
            'orderby' => 'slug',
            'parent' => 0
        );

        $categories = get_categories( $args );
        foreach ( $categories as $category ) {
            echo '<li><a href="' . get_category_link( $category->term_id ) . '" rel="bookmark"> <i class="glyphicon glyphicon-ok"> '  . $category->name . '</i>' . '' . $category->description . '</a></li>';
        }
    ?>
```
#### For Archives
File name must be [archive.php]
```php
<?php wp_get_archives(array('type'=>'monthly','limit'=>10,'order'=>'ASC'));?>
```
#### For Widget
For Register Widget
```php
    In [functions.php] file
    //Register Widget
function mySidebarWidget(){
    //home page sidebar one
    register_sidebar( array(
        'name'          =>esc_html__( 'Home Page Right  Widget', 'carnews' ), //Widget Name
        'description'   =>esc_html__( 'Home Page Right  Widget .....', 'carnews' ),//Widget Description
        'id'            => 'widget-home-right', //Widget Id 
        'before_widget' => '<div class="siderbar-widget">', 
        'after_widget'  => '</div>',
        'before_title'  => '<h4 class="sidebar-widget-title">',
        'after_title'   => '</h4> ',
    ) );
}

add_action('widgets_init','mySidebarWidget');
```
For show widget
```php
<?php dynamic_sidebar('widget-id');?> //
```
## Functions.php
```php
  //Menu Register
 //Initilize Menubar at any position
	function MyCarNewsMenu(){
		if (function_exists('register_nav_menu')){
			register_nav_menu('[Menu Class name]',__('[Menu Name]','carnews')); //Header Menu
			register_nav_menu('footer_menu',__('[Menu Name]','carnews')); //Footer Menu
		}
	}
	
add_action('init','[Function Name]');

//Add image upload ontion on admin panel
add_theme_support('post-thumbnails',array('post','page'));
set_post_thumbnail_size(200,200,true); //For thumb image size
add_image_size('image_id',300,300,true); //For Post image size
```