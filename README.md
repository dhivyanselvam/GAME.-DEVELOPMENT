# EX 2 : Bresenham‘s Line Drawing Algorithm
Register No: 212224230009
Name:AHAMADH SULAIMAN M
**AIM :**

 To  implement the Bresenham’s  algorithm for line using a c coding.

**ALGORITHM :**

   Step 1 : Start.
   
   Step 2 : Initialize the graphics header files and functions.

   Step 3 : Declare the required variables and functions.

   Step 4 : Get the four points for drawing a line namely x1,x2,y1,y2.

   Step 5 : Draw the line using the algorithm.

   Step  6 : Display the output.

   Step 7 : stop.

**Program :**
#include <stdio.h>
#include <conio.h>
#include <math.h>
#include <graphics.h>

int main() 
{ 
    int gd = DETECT, gm; 
    int xa, xb, ya, yb; 
    int dx, dy, x, y, xend, p, temp;

    initgraph(&gd, &gm, "C:\\Turboc3\\BGI"); 

    printf("Enter the first point (xa, ya):\n"); 
    scanf("%d%d", &xa, &ya); 

    printf("Enter the second point (xb, yb):\n"); 
    scanf("%d%d", &xb, &yb); 

    dx = abs(xb - xa); 
    dy = abs(yb - ya); 

    if (dx > dy) 
    { 
        // Line is more horizontal
        p = 2 * dy - dx; 

        if (xa > xb) 
        { 
            // Swap points if necessary
            temp = xa; xa = xb; xb = temp;
            temp = ya; ya = yb; yb = temp;
        } 

        x = xa; 
        y = ya; 
        xend = xb; 

        putpixel(x, y, 6); 

        while (x < xend) 
        { 
            x = x + 1; 
            if (p < 0) 
            { 
                p = p + 2 * dy; 
            } 
            else 
            { 
                y = (ya < yb) ? y + 1 : y - 1; 
                p = p + 2 * (dy - dx); 
            } 
            putpixel(x, y, 6); 
        } 
    }
    else 
    { 
        // Line is more vertical
        p = 2 * dx - dy;

        if (ya > yb) 
        { 
            // Swap points if necessary
            temp = xa; xa = xb; xb = temp;
            temp = ya; ya = yb; yb = temp;
        }

        x = xa; 
        y = ya; 
        xend = yb; 

        putpixel(x, y, 6); 

        while (y < xend) 
        { 
            y = y + 1; 
            if (p < 0) 
            { 
                p = p + 2 * dx; 
            } 
            else 
            { 
                x = (xa < xb) ? x + 1 : x - 1; 
                p = p + 2 * (dx - dy); 
            } 
            putpixel(x, y, 6); 
        } 
    }

    getch(); 
    closegraph(); 
    return 0; 
}


**Output :**
![Screenshot 2025-04-27 124910](https://github.com/user-attachments/assets/cfb92fea-01c8-42c8-b68f-a4717a8f992c)

 
**Result :**
Successfully implemented the Bresenham’s algorithm for line using a c program
