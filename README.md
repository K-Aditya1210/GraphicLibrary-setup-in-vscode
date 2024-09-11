# GraphicLibrary-setup-in-vscode
Step 1: Download [Solution-to-graphics.h](https://github.com/ullaskunder3/Solution-to-graphics.h)

To setup "graphics.h" in Visual Studio Code, download the zip file linked above to get all the required files.

extract the downloaded file, there will be three important files:

graphics.h
winbgim.h
libbgi.a
copy graphics.h and winbgim.h files then paste into MinGW/include folder, as shown in the image below.

path might be ("C:\MinGW\include")

![J](https://github.com/user-attachments/assets/f270596e-d0fa-4e69-9644-6a8653b71c37)

copy libbgi.a file then paste into MinGW/lib folder, as shown in the image below.

path might be ("C:\MinGW\lib")

![K](https://github.com/user-attachments/assets/4f343fd9-a9ad-4e18-a816-bd2a0f788795)

Step 2: Download [graphics.h-project-template](https://github.com/ullaskunder3/graphics.h-project-template)

download zip file from above link and then extract the downloaded file, now you can paste the extracted folder wherever you want and rename the folder name, as shown in the image below.

![L](https://github.com/user-attachments/assets/3a18a0b7-f3f4-4fdf-96be-cbd1ad32b317)

Now open copied folder and right click then choose open with code then your workspace will open in the visual studio code then trust the author to continue, as shown in the image below.

![N](https://github.com/user-attachments/assets/3d4a4219-ae97-41f5-91aa-5ce9b0be80ce)

Then the folder of your workspace will open in front of you, as shown in the image below.

![O](https://github.com/user-attachments/assets/2b230556-597f-481f-b3e2-484af93f9cce)

Now let's talk about src, build and .vscode. How these three folders do works?

Src : folder src contains source code files.
Build : folder build where compiled .exe file will be stored.
.vscode (DO NOT MODIFY ANYTHING IN THIS FOLDER) : .vscode includes c/cpp_properties.json and task.json that are required for compiling your computer graphics source code using graphics library.
Step 9: Download required extensions for visual studio code

Once visual studio code is installed, now we need some extensions so let's install.

click on the extension button then click on C/C++ extension from Microsoft as shown in the below image. You can search them up if it is not recommended.

then comes the second extension, Named “code runner”. install “code runner” extension by searching it up in visual studio code marketplace, as shown in the image below.

then the last extension comes our “exe runner”, for this, you have to search for “exe runner” in the search box of extensions and then install, as shown in the image below.

![M](https://github.com/user-attachments/assets/51a16555-6278-46aa-ae2a-cdefff7fa40f)

restart visual studio code after all three extensions have been installed, now we have successfully setup visual studio code for graphics programming.

Step 10: Now go to src folder and click on Hut.cpp and open the file

```
#include <stdio.h>
#include <stdlib.h>
#include <conio.h>
#include <graphics.h>
int main()
{
    int gm, x, y, gd = DETECT, i;
    // int midx, midy;
    int stangle = 45, endangle = 50;
    int radius = 50;
    
    char data[] = "C:\\MinGW\\lib\\libbgi.a"; //static file

    initgraph(&gd, &gm, data);
    x = getmaxx(); // to get the co-ordinates i.e. x & y
    y = getmaxy();
    cleardevice();
    line(200, 150, 350, 150);
    line(140, 200, 200, 150);
    line(140, 330, 140, 200);
    line(250, 200, 140, 200);
    line(200, 150, 250, 200);
    circle(196, 180, 15);
    setfillstyle(2, 14);
    floodfill(196, 180, 15);
    setfillstyle(1, 2);
    line(350, 150, 400, 200);
    floodfill(210, 180, 15);
    line(400, 200, 400, 330);
    line(140, 330, 400, 330);
    line(250, 200, 250, 330);
    line(250, 200, 400, 200); // Hut

    setfillstyle(5, 7);
    floodfill(260, 180, 15);
    line(170, 260, 170, 330);
    line(170, 260, 210, 260);
    setfillstyle(10, 9);
    floodfill(180, 250, 15);
    line(210, 260, 210, 330);
    setfillstyle(9, 9);
    floodfill(210, 250, 15);
    line(290, 110, 290, 150);
    line(310, 110, 310, 150);
    ellipse(300, 110, 0, 360, 10, 3); // Chemney

    setfillstyle(6, 8);
    floodfill(300, 120, 15);
    line(300, 250, 350, 250);
    line(300, 280, 350, 280);
    line(300, 250, 350, 280);
    line(300, 280, 300, 250);
    line(350, 280, 350, 250);

    setfillstyle(9, 9);
    floodfill(252, 300, 15);
    setfillstyle(8, 9);
    floodfill(342, 270, 15);

    setcolor(3);
    /* draw arc */
    arc(30, 300, stangle, endangle, radius);

    setcolor(7);
    line(5, 330, 600, 330);
    for (i = 0; i < 650; i = i + 10)
    {
        setcolor(4);
        settextstyle(7, 0, 5);

        char stringData1[] = "Home Sweet Home";

        outtextxy(0 + i, 390, stringData1);
        delay(100);
        setcolor(0);
        settextstyle(7, 0, 5);

        outtextxy(0 + i, 390, stringData1);
    }
    getch();
    closegraph();

    return 0;
}
```

Step 11: Now build and run the Code

To build from source code using/including graphics library, press “Ctrl+Shift+B” to run the build task you will get the executable file in build folder which will have same name as our source code file but with an extension of “.exe”, as shown in the image below.

![P](https://github.com/user-attachments/assets/e0f41061-52bc-4ef8-95eb-96e5ef3cc076)

now you will see the hut.exe file inside the build folder, you have to right click on this then click on run executable, as shown in the image below.

![Q](https://github.com/user-attachments/assets/127df6ba-4174-4bfa-baef-9cc3eefffc90)

Now your program will run and you will see a hut on the console that appears, as shown in the image below.

![R](https://github.com/user-attachments/assets/212753de-cc4e-42a4-988d-246d56879603)

now whenever you need to write a new code, just create a new file in src folder and write your source code in it the and build and run it just like we did for hut.cpp and hut.exe.

