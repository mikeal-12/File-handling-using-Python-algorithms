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

![image](https://github.com/mikeal-12/File-handling-using-Python-algorithms/assets/72464155/df69f99c-d06c-434d-b50c-dc5ce5beeff0)

The <code>.split()</code> function is called by appending it to a string variable. It works by converting the contents of a string to a list. The purpose of splitting <code>ip_addresses</code> into a list is to make it easier to remove IP addresses from the allow list. By default, the <code>.split()</code> function splits the text by whitespace into list elements. In this algorithm, the <code>.split()</code> function takes the data stored in the variable <code>ip_addresses</code>, which is a string of IP addresses that are each separated by a whitespace, and it converts this string into a list of IP addresses. To store this list, I reassigned it back to the variable <code>ip_addresses</code>.

## Iterating through the remove list
A key part of my algorithm involves iterating through the IP addresses that are elements in the <code>remove_list</code>. To do this, I incorporated a <code>for loop</code>:

![image](https://github.com/mikeal-12/File-handling-using-Python-algorithms/assets/72464155/bfc2773b-df1c-47f8-8ab5-0ec9302d9cc7)

The <code>for loop</code> in Python repeats code for a specified sequence. The overall purpose of the <code>for loop</code> in a Python algorithm like this is to apply specific code statements to all elements in a sequence. The <code>for</code> keyword starts the <code>for loop</code>. It is followed by the loop variable <code>element</code> and the keyword <code>in</code>. The keyword <code>in</code> indicates to iterate through the sequence <code>ip_addresses</code> and assign each value to the loop variable <code>element</code>. 

## Removing IP addresses that are on the remove list
My algorithm requires removing any IP address from the allow list, <code>ip_addresses</code>, that is also contained in <code>remove_list</code>. As there weren't any duplicates in <code>ip_addresses</code>, I was able to use the following code to do this:

![image](https://github.com/mikeal-12/File-handling-using-Python-algorithms/assets/72464155/03a142b5-772b-4be1-98f2-2290a872ae1a)

First, within my for loop, I created a conditional that evaluated whether or not the loop variable element was found in the <code>ip_addresses</code> list. I did this because applying <code>.remove()</code> to elements that were not found in <code>ip_addresses</code> would result in an error. 

Then, within that conditional, I applied <code>.remove()</code> to ip_addresses. I passed in the loop variable element as the argument so that each IP address that was in the <code>remove_list</code> would be removed from <code>ip_addresses</code>.

## Updating the file with the revised list of IP addresses 
As a final step in my algorithm, I needed to update the allow list file with the revised list of IP addresses. To do so, I first needed to convert the list back into a string. I used the <code>.join()</code> method for this:

![image](https://github.com/mikeal-12/File-handling-using-Python-algorithms/assets/72464155/a749b3d1-250b-4882-a7d3-32364579929e)

The <code>.join()</code> method combines all items in an iterable into a string. The <code>.join()</code> method is applied to a string containing characters that will separate the elements in the iterable once joined into a string. In this algorithm, I used the <code>.join()</code> method to create a string from the list <code>ip_addresses</code> so that I could pass it in as an argument to the <code>.write()</code> method when writing to the file <code>allow_list.txt</code>. I used the string <code>\n</code> as the separator to instruct Python to place each element on a new line. 
