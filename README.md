# C Pointer Concept Illustrator (CPCI)

![image](https://github.com/user-attachments/assets/cdfa6a48-56d3-4dba-8628-2b474f82fe69)

This is my Computer Science Special Problem (SP) application for the academic year 2023-2024. The project is a program designed to visualize C pointers, which features animations and interactive elements. It provides a dynamic representation of proper pointer usage, with checks to determine whether a pointer is appropriately employed or not. This tool is intended to be a valuable resource for students learning about pointers in C.



## Table of Contents

- [Interface Overview](#interface-overview)  
- [Usage Instructions](#usage-instructions)
- [Supported Code Formats](#supported-code-formats)  
- [Format Restrictions](#format-restrictions) 



## Interface Overview

![image](https://github.com/user-attachments/assets/62e1cec4-5a2f-4c4f-8b05-1fa3469dde16)

1. **Code Pane (Left side)** 
   - This is where you will put your C-pointer codes. Take note, however, of the supported codes for this program. You can learn more about it by going [here](#supported-code-formats). 
   - Once the play button has been clicked, a lexical and syntactical analysis of the codes will occur. If lexical or syntactical errors are present, they will be displayed in this area and you will be prompted to correct them. The navigation area will turn red to signify any lexical/syntax issues. On the other hand, if there were no detected lexical/syntax, the navigation area will turn to blue and animations will start from line 1. You can track the current line being animated in the codes area. 
2. **Level Visualization Pane (Middle)**

   - The **level visualization pane (LVP)** displays pointer- and non-pointer variables organized by levels. The main purpose of this area is to demonstrate that a pointer of level `n` can only point to a pointer of level `n-1` (assuming that `n-1` > 0). In essence, visually-speaking, a pointer at a specific level can only point to a variable at a level directly on their right side. Any other levels aside from this deemed invalid. 
3. **Box-and-pointer Diagram Pane (Right)**

   - The **box-and-pointer Diagram Pane (BDP)** aims to simulate how the resulting box-and-pointer diagrams would look on paper. Although seemingly unnecessary, this has been added to simulate how we would traditionally draw on paper without the level-specific organizations found on LVP.



## Usage Instructions

1. **Accept the terms of service** or agreement for using this software.
   ![image](https://github.com/user-attachments/assets/d65bbca0-5655-4dd4-8726-a14f7a141513)


2. **Fill the codes pane with supported C-pointer codes**. You can either write them manually, or import sample codes/previously-exported CPF files using the provided import button. Use the scroll bars or your scroll wheel to navigate the code like you would on VS code. In this non-playing state, you can also use the previous, next, or go-to-line buttons to browse through your code.   ![image](https://github.com/user-attachments/assets/8d479c5d-d0dc-4bd4-bb19-dbe2c17b33d7)

3. Once you are satisfied with your code, **click play** to animate the pointer animations. Just like what was mentioned previously, if lexical or syntactical errors have been highlighted in the codes pane, no animations will be displayed. You will need to edit these errors first before any animations could be displayed. Once a successful play operation has been established, the play button will now turn into a pause button.   ![image](https://github.com/user-attachments/assets/4d5489aa-46ed-4b36-80cc-c8c07c1f660e)

4. Animations per line are provided based on the context of current line. Notifications under the codes area button will also appear to provide further context. You can **use the pause button** at specific renderings to study their resulting diagrams and notifications.

   ![image](https://github.com/user-attachments/assets/893d1174-8a86-495a-82ab-9c014ae9cd13)

   Take note that clicking on the pause button will effectively freeze the current iteration, therefore you cannot use navigation buttons while on pause. 
   ![image](https://github.com/user-attachments/assets/a694a5f2-c943-4195-8194-894c71e93573)

5. If you want to navigate to specific lines in the codes pane, provided that the animations are not on pause, you can **use the next or previous buttons**. You can either **click on them once** to flash forward or backward 1 line, or **hold the button** to continuously navigate at a specific direction. Alternatively, you can use the "**Go to line**" button to go to a specific line.    ![image](https://github.com/user-attachments/assets/91922b83-9920-41ed-ae7a-9f01dc26d880)

   Take note, however, that you cannot move past an erroneous line in the animations even if there are more codes succeeding it.![image](https://github.com/user-attachments/assets/3176f2be-2193-4dc6-a4a9-baf3f97166b1)


6. If you want to change something in the code, you cannot simply click on the codes area and modify the codes. You must click the "**Stop Execution**" button first to halt all animations and enable the code editing mode.

   ![image](https://github.com/user-attachments/assets/446e5547-2d76-4169-8db7-db0c34cf7722)

7. If you want to save your current C pointer codes as a file which you can load in the future, you can use the "**Import as CPF File**" button. This will prompt you to save your current code as an external C-Pointer File (CPF) that you can save on your local computer. You can later load these files using the "**Import CPF Files/Sample Codes**" button. 

   ![image](https://github.com/user-attachments/assets/d91fe2e7-42c7-40f0-b1d3-fe5801aa5dd0)

---



## Other Noteworthy Buttons


![image](https://github.com/user-attachments/assets/3de0e373-44fd-475f-a9b2-8cecc3d16b86)


1. The "**center BDP horizontally**" check-box allows you to center the nodes in the Box-and-pointers Diagram Pane (BDP) relative to the x-axis. 
2. The "**center BDP vertically**" check-box allows you to center the aforementioned nodes relative to the y-axis.
3. Upon a successful exit of the application, the codes in the codes area are automatically saved to `user_preferences.json` for future reloading. This file is found in the root directory of the application. 
4. You can click on the "**Show User Manual**" to view the README.md file of this application which details everything you need to know about the application (this MD file).
5. You can click on the "**Review Terms of Service**" to review the agreements you accepted before entering the main area.
6. You can also check the **Credits** button to check on the developer, their respective adviser, and other special mentions.




## Supported Code Formats

There are only 3 varying formats supported in this application:

1. **Variable declarations without initialization**

   ``` C
   int var1;
   int *var2;
   ```

2. **Variable declarations with initialization**  

   ``` C
   // level-0 or normal variables
   int var1 = 10;
   int var2 = var1;
   int var3 = ***ptr; // assuming RHS is valid
   int var4 = **(&ptr); // assuming RHS is valid
   
   // pointer variables (level 1 and above)
   int *p1 = null;
   int *p2 = &var2;
   int *p3 = p1;
   int **p4 = &p1; 
   int **p5 = *p2; 
   int **p6 = *(&p3); 
   ```

3. **Value modification**  

   ``` C
   // level-0 or normal variables
   var1 = 10;
   var2 = var1;
   var3 = ***ptr; // assuming RHS is valid
   var4 = **(&ptr); // assuming RHS is valid
   
   // pointer variables (level 1 and above)
   p1 = null;
   p2 = &var2;
   p3 = p1;
   p4 = &p1; 
   p5 = *p2; 
   p6 = *(&p3); 
   
   // advanced pointer modifications (for all numbers of dereference operations '*')
   *p1 = null;
   *p2 = &var2;
   *p3 = p1;
   *(&p4) = &p1; 
   **(&p5) = *p2; 
   ***(&p6) = *(&p3); 
   ```



## Format Restrictions

1. **No arithmetic or binary operations allowed**

   ``` C
   var = 10 + 20;	// addition
   var = 10 - 20;	// subtraction
   var = 10 / 20;  // division
   var = 10 * 20;  // multiplication
   ...				// and other operations...
   ```

2. **No loops or other built-in functions**

   ``` C
   // for loops
   for (int i=0; i<10; i++) {
       printf("The value of i is %i.", i);
   }
   
   // while loops
   while (true) {
       printf("The value of str is %s.", &str);
       if (str[0] == 'a') break;
   }
   ```

3. **Only non-array int data-types are supported**

   ``` C
   char c = '1';			// not allowed
   char[] str = "data";	// not allowed
   int[] array;			// not allowed
   float value = 12.0;		// not allowed
   double num = 12.0;		// not allowed
   ...  
   ```

4. **Just like with any programming language, reserved keywords (null and int) cannot be used as variable names**

   ```C
   int int = 10;		// invalid!		
   int = 10;			// invalid!
   int null = 10;		// invalid!
   int null;			// invalid!
   int null = null;	// invalid!
   ```
