View online at https://github.com/lherbold/blender-readme/blob/main/README.md.

# Overview
Contained in this directory is a sample blender scene, `sky.blend`. This scene has a camera and a model (split into individual geometry pieces). There are also three scripts in the `/scripts` directory:
1) `export.py`: The python script that we will run inside blender to generate images.
2) `setup.command`: A script to run once that will install the necessary programs for processing images.
3) `blender.command`: A script that will launch blender, and enable scripting.

The `export.py` script works by scanning through all objects in the blender scene with the prefix `GEO` (we can change this as necessary), and exporting each one out individually as a separate image. The images are taken from a camera that must be present in the scene looking at the model.

# Automatic installation:
1) Double click on the `setup` script. If macOS prevents you from running the file, right click, and choose `Open`.
   1) This will install homebrew and imagemagick, an image converter tool necessary to perform post-processing.
2) Run the `blender` script to open a terminal window and start blender. Note that you _MUST_ start blender in this way for the script to work.
   1) Log output from running scripts in blender will appear in the terminal window.

# Manual installation:
1) Open the `terminal` application. (`Applications/Utilities/Terminal`)
2) Follow the instructions to install homebrew: https://brew.sh/
3) Install imagemagick by pasting the following in terminal: 
   1) `brew install imagemagick`
4) Open your shell configuration file by pasting one of the two following 'open' commands in terminal. Then edit the file by pasting the corresponding command onto a new line at the end. Your computer may have one or both of these files. Just edit one of them.
   1) `open -a TextEdit ~/.bash_profile`
      1) `function blender() { cd /Applications/Blender.app/Contents/MacOS && ./Blender }`
   2) `open -a TextEdit ~/.zshrc`
      1) `alias blender="cd /Applications/Blender.app/Contents/MacOS && ./Blender"`
5) Quit terminal and restart it. 
6) Type blender to open the program. Logs from the script will appear in terminal.

# Running the script:
1) Open the `scripting` tab in blender.
   1) If you don't see any code, you'll have to open the python file.
      1) Hit `Alt + O`. Find and double click on `export.py`.
2) Hit `Alt + P` to run the script. You should see output from the script in the terminal window you launched blender from.
3) Files should be output to a `spine/` folder in the same directory as the `.blend` file.
