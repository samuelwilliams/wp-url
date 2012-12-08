wp-url
======

When deploying WordPress websites from development or modifying existing WordPress instances, I often need to change the site name across all content. The query below does this.

    SET @old = 'dev.example.com', @new = 'www.example.com';
    
    UPDATE `wp_posts`    SET `post_content` = REPLACE(`post_content`, @old, @new);
    UPDATE `wp_posts`    SET `guid`         = REPLACE(`guid`,         @old, @new);
    UPDATE `wp_options`  SET `option_value` = REPLACE(`option_value`, @old, @new);
    UPDATE `wp_postmeta` SET `meta_value`   = REPLACE(`meta_value`,   @old, @new);

##License

This code is distributed under the WTFPL. Just do what you please.