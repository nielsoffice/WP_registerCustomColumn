# WP_registerCustomColumn
WordPress register or add a custom column on your post type and custom post type admin area

```PHP
$post_type = 'post';

// Register the columns.
add_filter( "manage_{$post_type}_posts_columns", function ( $defaults ) {
	
	$defaults['custom-one'] = 'Custom One';
	$defaults['custom-two'] = 'Custom Two';

	return $defaults;
} );

// Handle the value for each of the new columns.
add_action( "manage_{$post_type}_posts_custom_column", function ( $column_name, $post_id ) {
	
	if ( $column_name == 'custom-one' ) {
		echo 'Some value here';
	}
	
	if ( $column_name == 'custom-two' ) {
		// Display an ACF field
		echo 'my_acf_field';
	}
	
}, 10, 2 );

```

<br /> Also: 
<br /> https://github.com/nielsoffice/WP_customSearchFilter

<br /> Source: 
<br /> https://awhitepixel.com/blog/modify-add-custom-columns-post-list-wordpress-admin/
