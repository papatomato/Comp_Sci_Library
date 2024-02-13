# SFML Setup w/ MinGW, VSCode - 1_30_24

- https://www.youtube.com/watch?v=Ljhpsdz8Ouo
- drag and drop include and lib folders into created src folder of SFML directory in VScode
- ^^^ this is a failed option for SFML!!!

- attempting this instead - https://www.youtube.com/watch?v=Ptw1KKI9_Sg
- this was a success with the sfml test project!!!
- success with TEXT EDITOR!!!

## SUMMARY

- SFML has a bin folder that needs to be linked to the system PATH environment variables
- MING should also have bin linked to PATH as well. ALSO, include MING g++ to VS CODE default compiler configs -> ctrl + shift + p
- Set VS CODE includes in JSON project configs for SFML(whatever included libraries _not lib files btw_) and other HEADER files to remove squiggly warnings from code
- g++ -IC:/SFML-2.6.1/include -Isrc -c ./src/\*.cpp Editor.cpp
- .o files compile for each .cpp and are INDEPENDENTLY referenced in statement from header files (-I)
- use wildcard statement to include them all along with main.cpp
- g++ -LC:/SFML-2.6.1/lib ./build/\*.o -o editor.exe -lsfml-graphics -lsfml-window -lsfml-system
- finally link our SFML libs with -L, the object files folder via wildcard and the dynamic libraries of sfml -l to create exe (this won't be exe on mac)

[rocketbook notes](./rocketbooks/RB%202024-01-30%2019.36.47%20SFML_COMPILING.pdf)

---

# CSS - 1_31_24
 - __HTML URL Encoding__ - html urls cant have spaces, so they need to be encoded to handle those special characters. can be done [here](https://www.url-encode-decode.com/)
- to create links in .md files, enclose target text in brackets and add link in parenthesis after
- to open __MARKDOWN__ view in VSCode - ctrl + shift + V
---

- can add INTERNAL styling for a 1 page site in the __head__ section of the index page


## CSS Selectors

- ELEMENT, CLASS, ID, ATTRIBUTE, UNIVERSAL
### element
``` 
h1 {
  color: blue;  
}
```
### class
```
.red-text {
  color: blue;
}
```
### id
```
#main {
  color: red;
  }
```
### attribute
```
p[draggable="true"] {
  color: red;
  }
```
- universal -> \* ...selects everything
- MDN lists ATTRIBUTES for elements (e.g. https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li)

[rocketbook notes](./rocketbooks/RB%202024-01-31%2019.43.01%20css_selectors%20%5BCss%20selectors%5D.pdf)

# Fitness App, Python and Flask 1 - 2_1_24

- variables passed to index.html must be intiated in the def function scope of the render temp for that page
- Flask/Jinja to HTML syntax:
```
  @app.route("/")
  def home_page():
      exercises = exercises()
      return render_template('index.html', exercises=exercises)


      {% loop statement %}
      <li> {{ variable }} </li>
      {% endfor %}
```
[rocketbook notes](./rocketbooks/Flask_jinja_2_1_24%20[Flask].pdf)

# Blog App (Old Udemy) and Flask - 2_3_24

### url_for()
- used to generate URLs for routes, and returns the URL for the route
      **url_for('name of route function', args)**
- can be used in **href** elements
---
# CSS - 2_5_24
```
img {
  height: 200px;
  width: 200px;
}
```
# Fitness App - 2_7_24

### open() (PYTHON)
- returns an TextIOWrapper file object
- [more here](https://realpython.com/read-write-files-python/)
```
with open('dot_breeds.txt', 'r') as reader:
    # Read and print the entire file
    print(reader.read())
```
- the above code will open data as a __STRING__ 
- to use JSON, we need to use __json.load()__
- SHEETY was loading json data in with single quotes for keys -> had to convert the data as a string first use __json.loads__ to convert to json data
```
with open('file.json', 'r') as file:
    json_string = file.read()    

json_string = json_string.replace("'", '"')
fitness_data = json.loads(json_string)
```
[rocketbook notes](./rocketbooks/JSON_OPEN_2_8_24%20[File_READ_WRITE].pdf)

# EXP Feature and More Fitness App - 2_10_24

- reading and writing to file
```
with open("myfile.txt", "r+") as data:
```
- we can open read and write with "r+", use "a" to append to the end of the file, and "w" will overwrite everything
- use file.readlines() to read entire file into memory by line breaks that can be retrieved via index
- use FOR LOOPS to iterate line by line through an opened file as well
- used bootstrap cdn links to add bootstrap css styling to site

# WallJUMP game transfer from Pycharm to VSCode
- used builtin VSCode python interpreter options at bottom of window to create a venv and enable a local interpreter
- used pip install pygame to add into venv
- pygames got constants that need to have correct imports to access
``` 
from pygame.locals import * 
```

# Python Datetime - 2_12_2024
```datetime.strptime ('date string here', '%m/%d/%y')```
- the above converts a date-looking string to a datetime object
- use %Y if the year is four-digit
- strftime will convert a datetime object to string
- subtracting two datetime objects yields a deltatime object
- use an exception function to detect if a value is convertable to a datetime object first
```
def is_valid_datetime(strdate):
  try:
    convert_to_datetime(strdata)
    return True
  except ValueError:
    return False
```
[rocketbook notes](rocketbooks/RB%202024-02-12%2020.02.58%20[Datetime].pdf)