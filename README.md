## Project Description
At my organization(fictional), access to restricted content is controlled with an allow list of IP addresses. The <code>allow_list.txt</code> file identifies these IP addresses. A separate remove list identifies IP addresses that should no longer have access to this content. I created an algorithm to automate updating the <code>allow_list.txt</code> file and remove these IP addresses that should no longer have access. 

## Opening the file containing the allow list
For the first part of the algorithm, I opened the <code>allow_list.txt</code> file. First, I assigned this file name as a string to the <code>import_file</code> variable:
