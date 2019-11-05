# wordpress_sql

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
    
    
    
    
