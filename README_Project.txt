''''''''''''' INSTRUCTIONS ''''''''''''' 
1. Navigate to Project_Final/Project/mysite
2. Run "python manage.py runserver"
3. Copy the url provided, and append "builder" at the end, to obtain
   "http://127.0.0.1:8000/builder" ***IMPORTANT***
4. Ingredients have to be in singular form e.g. steak, not steaks.

''''''''''''' LIST OF MODULES USED '''''''''''''
1. Bootstrap
2. Django
3. Sqlite 3
4. Python Requests
5. BeautifulSoup4

''''''''''''' SUMMARY OF IMPORTANT FILES (BACK END) ''''''''''''' 

ignore_index.py
''''''''''''''
- Do not need to run. If ran, will replace the json files we have already
  included, as output filenames were hardcoded for our convenience.
- We used this to index food.com webpages and generate json files.
- Also generates a text file printing the results for debugging purposes.
- We ran this by calling "python3 ignore_index.py"
- Note that if a recipe does not have pictures of food associated with it 
  (4 such recipes in total), we used a placeholder picture.
  Input "milk, cocoa, vanilla extract, espresso" into the search page
  to see an example of this.
- We indexed a total of 2101 recipe pages.
- All code is original.

create_database.py
''''''''''''''''''
- Do not need to run. If ran, will replace the database files we have already
  included, as output filenames were hardcoded for our convenience.
- We used this to convert the json files from above to sql databases
  ignore_details.db and ignore_ingredients.db. These are already generated.
- We ran this by calling "python3 create_database.py ingredients" and
  "python3 create_database.py details".
- All code is original.

instacart.py
''''''''''''
- ignore_query.py calls this, so no need to run separately.
- This is used to first, login to instacart, and second, extract the details 
  of the first search result of a given ingredient.
- To run, one would need to go into ipython, and follow these steps:
    1) run instacart.py
    2) s = login()
    3) rv = get_missing_ingredient_details(s, "red bell pepper")
    4) print(rv)
- All code is original.

ignore_query.py
'''''''''''''''
- This is the only function called by the Django implementation
- This takes in a list of ingredients, and then searches a combination of
  sql and json files (already generated) to come up with appropriate recipe
  suggestions and details.
- The output is a list of ingredients, sorted in this order:
    1) Most number of user's ingredients used
    2) Highest rating according to food.com
- To run, one would need to go into ipython, and follow these steps:
    1) run ignore_query.py
    2) rv = go(["catfish", "garlic", "tomato", "chicken breast"])
- All code is original.

''''''''''''' SUMMARY OF IMPORTANT FILES (DJANGO) ''''''''''''' 

views.py
''''''''
- Main file in which we handle pages served to the user.
- More information in the header of file.

models.py
'''''''''
- File that holds models for our project.

urls.py
'''''''
- File that holds urlpatterns that our views link to.

All code in this segment was started off from the Django template, and
contains original work.

''''''''''''' SUMMARY OF IMPORTANT FILES (HTML/CSS) ''''''''''''' 

HTML files in Project_Final/Project/mysite/builder/template/builder:
- index.html
- results.html
- noresults.html
- about.html

CSS files in Project_Final/Project/mysite/builder/static/builder:
- cover.css
- results.css

Several of the HTML and CSS files listed here were based on templates from 
getbootstrap.com. Detailed citations are provided in the individual files.
