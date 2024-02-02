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

---

# CSS - 1_31_24

- can add INTERNAL styling for a 1 page site in the <head> section of the index page

## CSS Selectors

- ELEMENT, CLASS, ID, ATTRIBUTE, UNIVERSAL
- element -> h1 {
  color: blue;  
   }
- class -> .red-text {
  color: blue;
  }
- id -> #main {
  color: red;
  }
- attribute -> p[draggable="true"] {
  color: red;
  }
- universal -> \* ...selects everything
- MDN lists ATTRIBUTES for elements (e.g. https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li)

# Fitness App, Python and Flask 1 - 2_1_24

- variables passed to index.html must be intiated in the def function scope of the render temp for that page
- Flask/Jinja to HTML syntax:

  @app.route("/")
  def home_page():
      exercises = exercises()
      return render_template('index.html', exercises=exercises)

      {% loop statement %}
      <li> {{ variable }} </li>
      {% endfor %}
