# sourcemenu
A simple text menu user interface compitable with any Source engine game including HL2, TF2 and CS:GO
# Installation
1. Download and extract menu files
2. Go to Steam/steamapps/common/[game name]/[game root folder]/cfg<br>
For Team Fortress 2 it is Steam/steamapps/common/Team Fortress 2/tf/cfg<br>
3. Copy 'menu' folder to your 'cfg' folder
4. In your cfg folder, create or modify autoexec.cfg. In it, put the following command:<br>
<b>exec menu/core/loadmenu</b>
5. Go to menu/numbinds.cfg and paste any Numpad bindings you already have there. They will be executed when you close the menu.
5. While playing, press Num Delete to open/close menu and Numpad numbers to navigate
# Modification
To create new page, go to menu/templates/menupage.cfg and copy it's contents. 
Inside your 'menu' folder create a new .cfg file and paste the text from menupage.cfg in it. 
Fill option aliases with their functions by adding commands or alias names in them. For example:<br>
<b>alias "op1" "toggle viewmodel_fov 70 85 100; btn"<br></b>
Then go down to visible part (in it each line starts with 'echo' command) and add a short description to this option's function like this:<br>
<b>echo [1] - Toggle viewmodel_fov<br></b>
After that edit alias called lastapge. It opens last visited page when you re-open your menu. It must contain an exec command to execute current page from path starting from cfg folder. For example, you made file .../cfg/menu/newpage.cfg, so lastpage alias will look like:<br>
<b>alias lastpage "exec menu/newpage"</b><br>
For better visualisation of where is the current page in page tree, edit tree viewer in visible part:<br>
<b>echo ____________________________<br>
echo ""<br>
echo ../menu/newpage<br>
echo ____________________________</b><br>
Want to add your own scripts to menu? Either paste them in the beginning of the page where you want to execute them or execute once on game load from menu/core/loadmenu.cfg file with 'exec [pathtoscript]' command.
