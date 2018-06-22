# modx-redirect
ModX has become my goto Content Management System (CMS) in the last few days, while modx is a swiss-army-knife i still feel some of the requirements i had were not available or clearly documented in the ModX world.

One of my requirements from our CMS that hosts company learning data was to be able to send people to specific sections / pages when they login. This could be based on the group that they belonged to or the person, delberating what I wanted to do, I realised that quite a few of my team members held multiple roles, so it would be best if I took them to a specific person page. I looked around the Internet and found a few references of code, especially the pages at Bobs Guide [https://bobsguides.com/blog.html/2015/09/23/redirecting-users-on-login-iii/] but this did not work for me for whatever reason. One of my realisations with Bobs Guide code was that it was always detecting the web user as anonymous, and hence it could not take any action. I eneded up then writing this Snippet.

The Intention behind the snippet is simple, after the user logs in to the private areas of the website, they land on a default page (in my case this page has a resource-url value of 1) and I run this snippet on this page. The intention is to detect the username and then reference from Bobs Guide, detect the value that is stored in user settting LoginResource.

If there is no setting called LoginResource then it defaults to goto Resource Page 1, and if it finds a setting it redirects to that page.

To do this, I used the Following instructions from Bobs Guide 

**Creating a User Setting**
1. Follow these steps to create a user setting for each user:
2. Go to Manage -> Users on the Top menu
3. Right-click on a user and select "Update User"
4. Click on the the Settings tab, then on the "Create New" button
5. Enter LoginResource in both the Key and Name fields
6. In the Value field, put the ID of the resource you'd like to forward the user to on login
7. Click on the Save button at the upper right to save the user
8. Repeat for any other users you want to forward

While this may seem like a crazy way to do this, I have limited number of users that need to get redirected like this (specially those who hold multiple portfolios) and it is worth my time to do this, as I only have to do it when I have the user join the organisation and or start using the CMS.

The Code is pretty self explanatory, if you understand PHP
