# Technical assignment
The goal of this assignment is to complete as many tasks as possible listed below in the TODO list. 

## Scenario
A developer has built a landing page for a Live Video Shopping event, but there are still bugs to solve and improvements to make before the page can be used in production. We need you to update the code and fix the tasks listed in the TODO list further down on this page so everything is working as expected once launched. 

## Expectation
Here is the specification and high-level requirements for this landing page.

On this landing page, we are going to promote a Live Video Shopping show. 

The landing page consists of:
- **A countdown:** A graphical countdown. We should be able to set the date and time of the event. The countdown should disappear when done.
- **A header:** This header should have the value of 'We go live in' before the countdown is done. After the target time is passed, the value of the header should be 'We are live!'.
- **A CTA element:** A card including an image and a button. The whole card should be clickable and trigger the Bambuser Player with a recorded test show.

## Test the current behavior
### 1. Run the project
You are able to run the current project in either way below:
 - In the terminal, run `yarn start` within the project working directory 
 - Or, open the `src/index.html` in a browser

### 2. Modify the target time
In order to test the countdown on different occasions, in the `src/index.html`, you need to update the `data-date` and `data-time` to a closer time (e.g. current time + 1 min). So you can see how the count down behaves when it reaches the target time.
## TODO
  - [1]  Make the countdown loop stop once it reaches the target time. Currently, the countdown continues with minus values. --> *Implemented*
  - [2]  Make the countdown element disappear after the target time is reached.--> *Implemented*
  - [3]  The CTA element should show up when the countdown is done.--> *Implemented*
  - [4]  The default font for the landing page is set to `Neue Haas Grotesk Display`, but the font is not applied. Investigate why and provide a solution.--> *Implemented*
  - [5]  Center the `wrapper` element by modifying the CSS. The `wrapper` element is not fully centered (It is horizontally centered but not vertically). --> *Implemented*
  - [6]  The header text must be changed to 'We Are Live!' when the countdown is done.--> *Implemented*

## Questions
Once you have fixed the CTA button, you should be able to click it. On click, the Bambuser One-to-many player will be opened. When clicking a product in the player, you will see an error page. We need you to explain as much as possible in the field further down: 
   - What is the error?
   Ans: When I clicked on the product I got following error: demo.bambuser.shop refused to connect. 
		Then,When I checked console I got following three errors:
		1. Failed to load resource: the server responded with a status of 404 (Not Found)
		2. Refused to display 'https://demo.bambuser.shop/' in a frame because it set 'X-Frame-Options' to 'sameorigin'
		3. Uncaught DOMException: Blocked a frame with origin "http://127.0.0.1:5500" from accessing a cross-origin frame. at e.value (https://lcx-embed.bambuser.com/powered-by-bambuser-theme/embed.js:8:132275)
   
   - Why does it happen, what is the reason for this error?
   From the above errors 2 and 3 and troubleshooting it is understood that the site demo.bambuser.shop to which the request is sent does not allow or accepts requests from any other domain other than Origin.
      
   As seen from the Console, we can see that for the demo.bambuser.shop cookie’s SameSite attribute was not set or is invalid, it defaults to SameSite=Lax, which prevents the cookie from being sent in a cross-site request. This behavior protects user data from accidentally leaking to third parties and cross-site request forgery.
       
   - Potential solution(s)?
   We can Resolve this issue by updating the attributes of the cookie:
	--Specify SameSite=None and Secure if the cookie should be sent in cross-site requests. This enables third-party use.
	--Specify SameSite=Strict or SameSite=Lax if the cookie should not be sent in cross-site requests.
   

### Answer
      Place a brief explanation here. You can explain this further during the technical interview.


See how to reproduce the error: [Video](producing-iframe-error.mp4)




## How to deliver the assignment
- You will receive the assignment in a `.zip` file that you can unzip and start working on it.
- Make sure you read the README.md carefully before you start working on the tasks.
- *Would be nice* to use Git and commit your changes. You can use your local Git repository or a private remote repository.
- When you are done, make a zip archive of your project, including the .git directory *in case you chose to use Git*.
- There is no right or wrong, so, feel free to be creative while delivering the expectations.
- If you have any questions, reach out via email.