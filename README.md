# wordpress_sql
UPDATE `wp_users` SET `user_pass`= MD5('yourpassword') WHERE `user_login`='yourusername';

UPDATE wp_options
SET option_value = 'http://new-domain-name.com'
WHERE option_name = 'home';

UPDATE wp_options
SET option_value = 'http://new-domain-name.com'
WHERE option_name = 'siteurl';

UPDATE wp_posts
SET post_content = REPLACE(post_content,'http://old-domain-name.com','http://new-domain-name.com');

UPDATE wp_posts
SET guid = REPLACE(guid,'http://old-domain-name.com','http://new-domain-name.com');



# Wordpress_php

# Function.php

Add widgets

  register_sidebar( array('name' => 'LogoTop', 'before_widget' => '<div class="">', 'after_widget' => '</div>', 'before_title' => '<h3>', 'after_title' => '</h3>'));

Add Js
 wp_register_script('nachork', get_template_directory_uri() . '/js/category-list.js', array('jquery'), '1.0.0', true);
 wp_enqueue_script('nachork');
 
# anypage.php
 
Show the widgets
<?php if (!function_exists('dynamic_sidebar') || !dynamic_sidebar('Slider Full Width')) : endif; ?>

# Code Wordpres

    $rk_cat = get_the_category(); 
    $rk_mostrar_tour_single = $rk_cat[0]->cat_name;
    $current_post=wp_get_single_post();
    
# Default front-page file php
add code:
/* Template Name: Example Template */ 

#Obtain the title of post or page
<h2><?php the_title(); ?></h2>

#Obtain the post on WP
#<?php
		if ( have_posts() ) {

			// Load posts loop.
			while ( have_posts() ) {
				the_post();
			}

		};
?>
/**
 * Register Navigation
 */
    function register_my_menu() {
  register_nav_menu('header-menu',__( 'Header Menu' ));
}
add_action( 'init', 'register_my_menu' );
/**
 * Register Custom Navigation Walker (Bootstrap)
 */
function register_navwalker(){
	require_once get_template_directory() . '/php-bootstrap/class-wp-bootstrap-navwalker.php';
}
add_action( 'after_setup_theme', 'register_navwalker' );
	

$pagename = get_query_var('pagename');
    
