## Project Description
At my organization(fictional), access to restricted content is controlled with an allow list of IP addresses. The <code>allow_list.txt</code> file identifies these IP addresses. A separate remove list identifies IP addresses that should no longer have access to this content. I created an algorithm to automate updating the <code>allow_list.txt</code> file and remove these IP addresses that should no longer have access. 

## Opening the file containing the allow list
For the first part of the algorithm, I opened the <code>allow_list.txt</code> file. First, I assigned this file name as a string to the <code>import_file</code> variable:

![image](https://github.com/mikeal-12/File-handling-using-Python-algorithms/assets/72464155/472bd233-8e7c-4115-96e4-e9f3b961e870)

Then, I used a <code>with</code> statement to open the file:

![image](https://github.com/mikeal-12/File-handling-using-Python-algorithms/assets/72464155/8a1e2151-d86a-407a-8db6-94ec10b2bb0f)

In my algorithm, the <code>with</code> statement is used with the <code>.open()</code> function in <code>read</code> mode to open the allow list file for the purpose of reading it. The purpose of opening the file is to allow me to access the IP addresses stored in the allow list file. The with keyword will help manage the resources by closing the file after exiting the with statement. In the code <code>with open(import_file, "r") as file:</code>, the <code>open()</code> function has two parameters. The first identifies the file to import, and then the second indicates what I want to do with the file. In this case, <code>r</code> indicates that I want to read it. The code also uses the <code>as</code> keyword to assign a variable named <code>file</code>; file stores the output of the <code>.open()</code> function while I work within the <code>with</code> statement.
