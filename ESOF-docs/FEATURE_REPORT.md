#Reddit - Feature Implemented

###Description of the feature
All members of the group use reddit frequently. We all, in one time or another, wanted to share a post or thread onto facebook, but never really knew how. After searching for that, we finally found it, below the link of the post, but its visibility wasn't the best and it's not used by redditors. Moved by this fact, we decided to implement the same feature, but with more visibility, right on the tab menu, like this:
![feature](resources/feature.png)


Currently, reddit has something like this on the tab menu:
![not_feature](resources/not_feature.png)


And the share functionality, on live:
![current_share](resources/current_share.png)


The feature is easy to use, as you only need to press the button "Share on Face", and it will redirect you to facebook.com and it will let you share the current link on Facebook.

###Feature implementation
The feature implemented is an additional "li" on "r2/r2/templates/navmenu.html" that consists on a button named "Share on face" that uses a javascript function that redirects the user to a facebook share application to share the current reddit page you were in to anywhere you want on facebook.