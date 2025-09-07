LVGL Custom Fonts – Handleiding / Guide
Een eenvoudige en praktische gids voor het gebruik van eigen fonts in LVGL 9.3.
Getest met Visual Studio 2022 en Arduino-projecten.

🇳🇱 Nederlandse Handleiding
🔧 Stap 1: Font genereren
Gebruik de LVGL font converter (online of offline) om je TTF/OTF-bestand om te zetten naar een .c bestand.
🧼 Stap 2: .c bestand aanpassen
Open het gegenereerde .c bestand.
Vervang het blok bovenaan (met #ifdef en #include) door één regel:
#include "lvgl.h"


📁 Stap 3: Bestand toevoegen aan je project
- Visual Studio 2022: Voeg het .c bestand toe via Add Existing Item als "Source File".
- Arduino: Plaats het .c bestand in de root van je projectmap.
🌍 Stap 4: Font beschikbaar maken
Globaal (voor heel je project):
In lv_conf.h, voeg toe:
#define LV_FONT_CUSTOM_DECLARE LV_FONT_DECLARE(customfont1) LV_FONT_DECLARE(customfont2)


Gebruik de juiste fontnaam zoals gedefinieerd onderaan het .c bestand:
const lv_font_t customfont1 = {
    ...
};


Lokaal (alleen in één source file):
Voeg bovenin je .c of .cpp bestand toe:
LV_FONT_DECLARE(customfont1);


🖋️ Stap 5: Font gebruiken in je code
Stel het font in voor een object:
lv_obj_set_style_text_font(objectnaam, &customfont1, LV_PART_MAIN);



🇬🇧 English Guide
🔧 Step 1: Generate the font
Use the LVGL font converter (online or offline) to convert your TTF/OTF file into a .c file.
🧼 Step 2: Modify the .c file
Open the generated .c file.
Replace the top block (with #ifdef and #include) with a single line:
#include "lvgl.h"


📁 Step 3: Add the file to your project
- Visual Studio 2022: Add the .c file via Add Existing Item as a "Source File".
- Arduino: Place the .c file in the root of your project folder.
🌍 Step 4: Make the font available
Globally (for the entire project):
In lv_conf.h, add:
#define LV_FONT_CUSTOM_DECLARE LV_FONT_DECLARE(customfont1) LV_FONT_DECLARE(customfont2)


Use the correct font name as defined at the bottom of the .c file:
const lv_font_t customfont1 = {
    ...
};


Locally (only in one source file):
At the top of your .c or .cpp file, add:
LV_FONT_DECLARE(customfont1);


🖋️ Step 5: Use the font in your code
Apply the font to an object:
lv_obj_set_style_text_font(objectname, &customfont1, LV_PART_MAIN);




Doe er je voordeel mee en hopelijk werkt dit ook voor jou.
