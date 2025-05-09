## SignUpLogin

### Explanation  

#### HTML (```<body>```):
##### Signup Form: A form with name, email, password, and confirm password fields.
##### Login Form: A form with email and password fields.
##### Dashboard: A page displaying user information (name, email, and unique info). Initially hidden.
##### Switch Buttons: Buttons to toggle between the signup and login forms.
##### Dark Mode Toggle: A checkbox to switch between light and dark mode.  

#### CSS (```<style>```):
##### Responsive Design: Uses ```max-width``` and percentages to adapt to different screen sizes.
##### Flexbox: Used for layout and alignment of form elements.
##### Error Messages: Styled with a red color and are hidden by default.
##### Buttons: Styled with hover effects (darker shade and slight elevation). The sign up button is disabled until all the fields are valid.
##### Transitions: Smooth color and transform transitions for better user experience.
##### Dark Mode: Styles for dark mode, including background, text, and box shadows.  

#### JavaScript (```<script type="text/babel">```):  

##### Variables: Gets HTML elements and retrieves stored user data from ```localStorage```.  

##### Validation Functions:  
```validateName()```: Checks if the name is not empty and has at least 2 characters.  
```validateEmail()```: Checks for a valid email format using a regular expression.  
```validatePassword()```: Checks for minimum length (8), and ensures the password contains at least one lowercase letter, one uppercase letter, one number, and one special character.  
```validateConfirmPassword()```: Checks if the password confirmation matches the password.  
```displayErrorMessage()```: Displays an error message below the input field.  
```clearErrors()```: Clears all error messages.  

##### Form Handling:  
```handleSignup(event)```: Validates the signup form, checks for an existing user, stores the new user in localStorage, and displays the dashboard.  
```handleLogin(event)```: Validates the login form, retrieves the user from localStorage, and displays the dashboard.  
```showDashboard()```: Hides the signup and login forms and displays the user dashboard.  
```showLoginForm()```: Displays the login form and hides the signup form and dashboard.  
```showSignupForm()```: Displays the signup form and hides the login form and dashboard.  
```handleLogout()```: Removes the current user from localStorage and redirects to the signup form.  
```toggleDarkMode()```: Switches between light and dark mode by adding/removing a class to the body and other elements. It also saves the user's preference to localStorage.   

##### Event Listeners:  
```signupForm.addEventListener('submit', handleSignup)```: Handles the signup form submission.  
```loginForm.addEventListener('submit', handleLogin)```: Handles the login form submission.  
```switchToLoginButton.addEventListener('click', showLoginForm)```: Switches to the login form.  
```switchToSignupButton.addEventListener('click', showSignupForm)```: Switches to the signup form.  
```logoutButton.addEventListener('click', handleLogout)```: Handles the logout button click.  
```darkModeSwitch.addEventListener('change', toggleDarkMode)```: Handles changes to the dark mode toggle.  

##### Initial Setup:  
Checks for a logged-in user in ```localStorage``` and displays the dashboard if found. Otherwise, it displays the signup form.  
Applies the user's dark mode preference from ```localStorage```, if any.
