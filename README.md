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
