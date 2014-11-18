sluggit
=======

Simple gem for Rails projects to slugify URLs based on any model attribute

Pre-requisite:
The model that needs to be slugified has to have a column titled 'slug' in its table.

If it doesn't, follow steps 1 through 3, else, skip to 4:

1. Add the 'slug' column to the model table using a migration `rails g migration add_slug_column_to_table`
2. Add the following content to the change method in the generated migration file:
`add_column :users, :slug, :string`
Note: Replace the `:users` with the appropriate model name

3. Run `bundle exec rake db:migrate` to add the column

4. Add the line `require 'slugable'` to application.rb to enable inclusion in any model

5. Add the following code to the model class which you want to slugify:

``` ruby
include Slugable
set_slug_column_to :username
```
Note: replace `:username` with any attribute name for the model you want to use to 'slugify' it.
