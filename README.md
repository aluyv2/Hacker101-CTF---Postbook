# Hacker101-CTF---Postbook

CTF Name: Postbook
Resource: Hacker101 CTF
Difficulty: Easy
Number of Flags: 7

Flag0
Goal: The person with username "user" has a very easy password...
Acquired By: username:user and password:password.

Flag1
Goal: Try viewing your own post and then see if you can change the ID
Acquired By: Navigating to a URL with a different 'id=#" than my own. navigate to a URL for a post by id: http://....../index.php?page=profile.php&**id=d**

Flag2
Goal: You should definitely use "Inspect Element" on the form when creating a new post
Acquired By: Changing a hidden field in a form lead to the capture of this flag. By changing the user_id's value this allowed me to post as someone else.
![image](https://user-images.githubusercontent.com/123699576/215363944-29147e20-193a-4fc3-8207-7eadfb5e1f93.png)



Flag3
Goal: 189 * 5
Acquired By: 189 * 5 = 945... This is the ID of a mystery post. Change the post ID like before to 945 and find your flag. Thoughts: It is a common tactic to number posts like this but it might be a mistake if a post is 'private' and can be viewed by simply changing the id number.

Flag4
Goal: You can edit your own posts, what about someone else's?
Acquired By: Like the 'hidden' field before I tried changing the id of the edit button
![image](https://user-images.githubusercontent.com/123699576/215364064-bfa75c90-6a17-413c-9cbc-4c31e0751532.png)



Flag5
Goal: The cookie allows you to stay signed in. Can you figure out how they work so you can sign in to user with ID 1?
Acquired By: When you inspect the page on login you can see the cookie id=someMD5HashAgain where the hash is the user id. If we use an addon that allows us to edit the cookie we can get the MD5 hash for the number 1 and replace the cookie with the new hash. On refresh the site will go off of the new cookie set and log in a user 1.
![image](https://user-images.githubusercontent.com/123699576/215364082-26091655-e6a7-4a4a-a562-b5d07ca8de2a.png)


Flag6
Goal: Deleting a post seems to take an ID that is not a number. Can you figure out what it is?
Acquired By: Like Flag4 I needed to change the id of the delete button and that allowed the flag to be acquired. This one was a big difficult though as the id was a hash. MD5 to be specific. The thing with MD5 hashs is that they always produce the same output so by decoding it and then picking the hash for a different user is simple.
![image](https://user-images.githubusercontent.com/123699576/215363918-9348cdba-9872-45c9-9066-d491148407ae.png)

