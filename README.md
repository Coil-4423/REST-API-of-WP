# REST-API-of-WP
To get the REST API address of your WordPress site, you can follow this simple guide. WordPress provides an API out of the box, and the base URL for all REST API endpoints is structured as follows:

### General Format:
```
https://yourwebsite.com/wp-json/wp/v2/
```

### Step-by-Step Guide to Finding the API Address:

1. **Base API URL**: 
   - If your WordPress site is hosted at `https://example.com`, then the base URL for the REST API would be:
     ```
     https://example.com/wp-json/
     ```

2. **Specific Endpoints**: 
   You can append different endpoints depending on the type of data you want to retrieve. Below are a few common examples:

   - **Posts**: 
     ```
     https://example.com/wp-json/wp/v2/posts
     ```
     This retrieves a list of posts.

   - **Custom Post Type (e.g., Projects)**:
     If you have registered a custom post type (like `project`), the API endpoint for that post type will be:
     ```
     https://example.com/wp-json/wp/v2/projects
     ```

   - **Pages**:
     ```
     https://example.com/wp-json/wp/v2/pages
     ```

   - **Categories**:
     ```
     https://example.com/wp-json/wp/v2/categories
     ```

   - **Taxonomies (e.g., Project Types)**:
     If you registered a custom taxonomy like `project_type`, the endpoint would be:
     ```
     https://example.com/wp-json/wp/v2/project_type
     ```

3. **Custom REST Base** (for Custom Post Types or Taxonomies):
   If you've set a custom `rest_base` in your post type or taxonomy, replace the default base (`posts`, `categories`, etc.) with your custom base. For example:
   
   ```php
   'rest_base' => 'my-projects'
   ```
   The API endpoint would then be:
   ```
   https://example.com/wp-json/wp/v2/my-projects
   ```

### Example:
If your WordPress site URL is `https://mycoolsite.com`, and you want to fetch data from your custom post type `projects`, the API URL will look like this:
```
https://mycoolsite.com/wp-json/wp/v2/projects
```

### Testing the API:
You can test the API by typing the above URL into your browser or using tools like [Postman](https://www.postman.com/) or [cURL](https://curl.se/) to make HTTP requests.

### Important Notes:
1. **Permalink Settings**: For the REST API to work, WordPress needs to have permalinks enabled (anything except `Plain` in the permalink settings).
2. **Publicly Queryable**: The post type or taxonomy must be `public` and `publicly_queryable` for the API to return the data.
3. **Authentication**: If you are trying to access private data (e.g., private posts or user details), you will need proper authentication (e.g., via OAuth or Application Passwords).

This method allows you to quickly find the correct API address for accessing your WordPress site's data programmatically.
