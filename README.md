# Hacker101-CTF---Postbook

***Description:***

	CTF Name: Postbook 

	Resource: Hacker101 CTF 

	Difficulty: Easy 

	Number of Flags: 7 






***Flag 0***

- **Goal:** The person with username "user" has a very easy password...

- **Acquired By:** username:user and password:password. Classic dictionary attack (with the possibility of brute force if needed).

***Flag 1***

- **Goal:** Try viewing your own post and then see if you can change the ID

- **Acquired By:** Navigating to a URL with a different 'id=#". ID can be found in URL: http://....../index.php?page=profile.php&**id=d**

***Flag2***

- **Goal:** You should definitely use "Inspect Element" on the form when creating a new post
- **Acquired By:** Changing a hidden field in a form lead to the capture of this flag. By changing the user_id's value this allowed access to post as someone else.

  - ![image](https://user-images.githubusercontent.com/123699576/215363944-29147e20-193a-4fc3-8207-7eadfb5e1f93.png)


***Flag 3***

- **Goal:** 189 * 5

- **Acquired By:** 189 * 5 = 945. This is the ID of a hidden post. Change the post ID.


***Flag 4***

- **Goal:** You can edit your own posts, what about someone else's?

- **Acquired By:** Select the 'hidden' field. Changed the post ID in the URL to the admin post.

  - ![image](https://user-images.githubusercontent.com/123699576/215364064-bfa75c90-6a17-413c-9cbc-4c31e0751532.png)


***Flag 5***

- **Goal:** The cookie allows you to stay signed in. Can you figure out how they work so you can sign in to user with ID 1?

- **Acquired By:** Inspecting the page upon login under 'network' there is a cookie ID: id=MD5hash. Using a hash translator and cookie editor add-on from FireFox, the cookie can be changed to the hash of 1 in order to sign in as 'admin' after refreshing the page.

  - ![image](https://user-images.githubusercontent.com/123699576/215364082-26091655-e6a7-4a4a-a562-b5d07ca8de2a.png)


***Flag 6***

- **Goal:** Deleting a post seems to take an ID that is not a number. Can you figure out what it is?

- **Acquired By:** Signed out from previous flag. The id of the delete button can be changed in inspect element. The hash ID can be converted to another MD5 hash of a post ID. In this case the post '2' was deleted to reveal the flag.

  - ![image](https://user-images.githubusercontent.com/123699576/215363918-9348cdba-9872-45c9-9066-d491148407ae.png)

- **CTF complete!**

  - ![image](https://user-images.githubusercontent.com/123699576/215364771-cbb17ea7-c0a9-48b3-8463-720caa8ed467.png)
