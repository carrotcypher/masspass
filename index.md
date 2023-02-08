# MassPass

MassPass is a website mass-password reset helper.

## Problem

Good password management and sanity demands a unique password for each service and website we use. As password managers become more common for storing passwords for various websites, the amount of unique passwords stored for each user increases, often into the hundreds.

Until proposals such as [A Well-Known URL for Changing Passwords, W3C First Public Working Draft, 27 September 2022](https://www.w3.org/TR/change-password-url/) and other APIs and automation eventually allow for resetting passwords en masse, whenever you want to change all passwords on your accounts you presently are stuck doing it manually.

The biggest problem is when an email address or password manager's vault file is compromised and you believe the passwords in it are compromised and must be changed. How do you go through 500 websites and change all the passwords immediately? 

## Solution (sort of)

While this web app is not a truly automated mass password changer that you can just set some settings and walk away while it works, it does attempt to save time by automating much of the process and simplifying what is needed from the user.

It will attempt to:

* convert your existing exported Bitwarden vault JSON file into a simplified list of domain names
* find the known password reset pages for those domains
* open a new window to that website each time you tell it you're ready to move to the next one

## How does it work?

1. Expot Bitwarden vault to JSON
2. Copy/paste contents of file to MassPass "Load" window and press "Load"
3. MassPass goes through each vault item and extracts the relevant domain, adding it to the "Domains" window
4. Press "Start" and the process begins with the first domain. MassPass opens a new window to that domain.
5. Each time you press "Next", it opens a new window to the next domain in line.
6. (Optional) If the website's password reset URL is known to MassPass, it will attempt to take you to that password reset page directly to save even more time

## What does it not do?

* It cannot know which account you are resetting the password for, you need to choose based on what is displayed in Bitwarden.
* It does not guarantee the password you reset to is updated in Bitwarden correctly (you always need to do this yourself when updating passwords via a password manager)

## While you're changing passwords, what should you consider?

* Make sure Bitwarden has updated to the new password
* If it's a website with multiple domains (e.g. a website that uses a master company as identity management for a product website with a different domain) make sure to add both when changing the password to avoid future confusion or losing access
* Consider enabling 2FA for your accounts while you're changing the passwords
* Consider checking the email address for the website account in question as it might be an old, compromised one rendering the password change fruitless
* Consider changing your Bitwarden master password as well

## License

![Creative Commons Zero v1.0 Universal](https://i.creativecommons.org/p/zero/1.0/88x31.png)

Creative Commons Zero v1.0 Universal

"No rights reserved"
