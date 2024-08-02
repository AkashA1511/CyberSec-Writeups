# TryHackMe Walking An Application Walkthrough

In this room, you will learn how to manually review a web application for security issues using only the built-in tools in your browser. Automated security tools and scripts often miss many potential vulnerabilities and useful information.

## Tools Used in This Room:
- **View Source**: View the human-readable source code of a website.
- **Inspector**: Inspect page elements and make changes to view usually blocked content.
- **Debugger**: Inspect and control the flow of a page's JavaScript.
- **Network**: See all the network requests a page makes.

---

## Exploring The Website

As a penetration tester, your role when reviewing a website or web application is to discover features that could potentially be vulnerable and attempt to exploit them to assess whether or not they are. These features are usually parts of the website that require some interactivity with the user.

### Example Site Review: Acme IT Support Website

| Feature                | URL                    | Summary                                                                 |
|------------------------|------------------------|-------------------------------------------------------------------------|
| Home Page              | /                      | Summary of what Acme IT Support does with a company photo of their staff.|
| Latest News            | /news                  | List of recently published news articles by the company. Each news article has a link with an id number, e.g., /news/article?id=1.|
| News Article           | /news/article?id=1     | Displays the individual news article. Some articles are reserved for premium customers only.|
| Contact Page           | /contact               | Contains a form for customers to contact the company. Fields: name, email, and message.|
| Customers Login        | /customers/login       | Contains a login form with username and password fields.                |
| Customer Signup        | /customers/signup      | Contains a user-signup form with username, email, password, and password confirmation fields.|
| Customer Reset Password| /customers/reset       | Password reset form with an email address input field.                  |
| Customer Dashboard     | /customers             | Contains a list of the user's tickets submitted to the IT support company and a "Create Ticket" button.|
| Create Ticket          | /customers/ticket/new  | Contains a form with a textbox for entering the IT issue and a file upload option to create an IT support ticket.|
| Customer Account       | /customers/account     | Allows the user to edit their username, email, and password.            |
| Customer Logout        | /customers/logout      | Logs the user out of the customer area.                                 |

---

## Viewing The Page Source

The page source is the human-readable code returned to our browser/client from the web server each time we make a request. It consists of HTML, CSS, and JavaScript, which tells our browser what content to display, how to show it, and adds interactivity with JavaScript.

### How to View the Page Source:
- Right-click on the page and select "View Page Source".
- Put `view-source:` in front of the URL (e.g., `view-source:https://www.google.com/`).
- Find the option in your browser menu, usually under developer tools or more tools.

### Viewing Page Source Example:
- At the top of the page, you may see comments enclosed in `<!-- -->`. These are messages left by the developer and do not display on the webpage.
- Look for links written in anchor tags `<a>` with the URL in the `href` attribute.
- External files such as CSS, JavaScript, and Images are included using HTML code.

### Flags in Page Source:
1. **Flag from the HTML comment**: `THM{HTML_COMMENTS_ARE_DANGEROUS}`
2. **Flag from the secret link**: `THM{NOT_A_SECRET_ANYMORE}`
3. **Directory listing flag**: `THM{INVALID_DIRECTORY_PERMISSIONS}`
4. **Framework flag**: `THM{KEEP_YOUR_SOFTWARE_UPDATED}`

---

## Developer Tools - Inspector

### Inspector:
- Provides a live representation of what is currently on the website.
- Allows you to edit and interact with page elements.
- Useful for debugging issues and viewing content hidden behind paywalls.

### Example:
- On the Acme IT Support website, click into the news section.
- Right-click on the premium notice and select "Inspect".
- Locate the `DIV` element with the class `premium-customer-blocker`.
- Change `display: block` to `display: none` to reveal the content underneath.

#### Flag behind the paywall: `THM{NOT_SO_HIDDEN}`

---

## Developer Tools - Debugger

### Debugger:
- Intended for debugging JavaScript.
- Allows you to inspect and control the flow of a page's JavaScript code.
- In Chrome, this feature is called "Sources".

### Example:
- On the contact page, notice a rapid flash of red on the screen.
- In the debugger, find the `flash.min.js` file in the `assets` folder.
- Use the "Pretty Print" option to format the code.
- Find the line `flash['remove']();` and set a breakpoint.
- Refresh the page to reveal the red box with the flag.

#### Flag in the red box: `THM{CATCH_ME_IF_YOU_CAN}`

---

## Developer Tools - Network

### Network Tab:
- Keeps track of every external request a webpage makes.
- Useful for monitoring AJAX requests and other network activity.

### Example:
- On the contact page, fill in the contact form and press the "Send Message" button.
- Examine the new entry on the network tab to find the flag.

#### Flag shown on the contact-msg network request: `THM{GOT_AJAX_FLAG}`

