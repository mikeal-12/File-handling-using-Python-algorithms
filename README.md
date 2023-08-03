## Project Description
At my organization(fictional), access to restricted content is controlled with an allow list of IP addresses. The <code>allow_list.txt</code> file identifies these IP addresses. A separate remove list identifies IP addresses that should no longer have access to this content. I created an algorithm to automate updating the <code>allow_list.txt</code> file and remove these IP addresses that should no longer have access. 

## Opening the file containing the allow list
For the first part of the algorithm, I opened the <code>allow_list.txt</code> file. First, I assigned this file name as a string to the <code>import_file</code> variable:

![image](https://github.com/mikeal-12/File-handling-using-Python-algorithms/assets/72464155/472bd233-8e7c-4115-96e4-e9f3b961e870)

Then, I used a <code>with</code> statement to open the file:

![image](https://github.com/mikeal-12/File-handling-using-Python-algorithms/assets/72464155/8a1e2151-d86a-407a-8db6-94ec10b2bb0f)

In my algorithm, the <code>with</code> statement is used with the <code>.open()</code> function in <code>read</code> mode to open the allow list file for the purpose of reading it. The purpose of opening the file is to allow me to access the IP addresses stored in the allow list file. The with keyword will help manage the resources by closing the file after exiting the with statement. In the code <code>with open(import_file, "r") as file:</code>, the <code>open()</code> function has two parameters. The first identifies the file to import, and then the second indicates what I want to do with the file. In this case, <code>r</code> indicates that I want to read it. The code also uses the <code>as</code> keyword to assign a variable named <code>file</code>; file stores the output of the <code>.open()</code> function while I work within the <code>with</code> statement.

## Reading the file contents
In order to read the file contents, I used the <code>.read()</code> method to convert it into the string.

![image](https://github.com/mikeal-12/File-handling-using-Python-algorithms/assets/72464155/c5f14d56-de60-4148-a01d-2245b2dee366)

When using an <code>.open()</code> function that includes the argument <code>r</code> for <code>read</code>, I can call the <code>.read()</code> function in the body of the <code>with</code> statement. The <code>.read()</code> method converts the file into a string and allows me to read it. I applied the <code>.read()</code> method to the file variable identified in the <code>with</code> statement. Then, I assigned the string output of this method to the variable <code>ip_addresses</code>. 

In summary, this code reads the contents of the <code>allow_list.txt</code> file into a string format that allows me to later use the string to organize and extract data in my Python program.

## Converting the string into a list
In order to remove individual IP addresses from the allow list, I needed it to be in list format. Therefore, I next used the <code>.split()</code> method to convert the <code>ip_addresses</code> string into a list:

