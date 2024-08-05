# 1. Define the Post Model
      In models.py of your blog app, define the Post model
# 2. Perform Database Migrations
      Run the following commands in your terminal to create and apply the migrations
      python manage.py makemigrations
      python manage.py migrate

# 3. Create Views to Display Posts
      In views.py, create views to display the list of posts and the details of a single post.

# 4. Set Up URLs
In the blog app, create a urls.py file
Include the blog app's URLs in the project's urls.py

# 5. Create Templates
Create a templates directory inside your blog app, with subdirectories and files as follows:
      blog/templates/post_list.html
      blog/templates/post_detail.html
      
# 6. Use Django Admin to Manage Posts
In admin.py, register the Post model with the Django admin site:
# Breakdown of the Code:
# 1. return render(request, ...):

This function is used to render an HTML template with a given context.
It takes the request object as its first argument, which represents the current HTTP request that triggered this view.

# 2. 'template/post_list.html':
This is the path to the HTML template that will be rendered.
In this case, it points to a file named post_list.html located inside the blog/templates/ directory.
{'posts': posts}:

# 3. This is the context dictionary that gets passed to the template.
It maps the variable name posts (used in the template) to the value of the posts variable defined in the view.
In the context of this view, posts is likely a QuerySet containing a list of Post objects retrieved from the database.

# What This Line Does:
It retrieves all the blog posts from the database (via posts = Post.objects.all()).
It then renders the post_list.html template, passing the posts data to the template.
The template can use the posts variable to display the list of posts.

# {% for post in posts %}
            <li><a href="{% url 'post_detail' post.pk %}">{{ post.title }}</a> by {{ post.author }}</li>
        {% endfor %}
        This code loops through the posts variable passed from the view and displays each post's title.
