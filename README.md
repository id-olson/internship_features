# internship_features

### Details
I did web, mobile, frontend, backend, UI/UX, AWS, and database work in my internship at ChartX, during my spring semester of junior year (2024). While I am not able to share any code, I have included some screenshots of mobile app screens with components I designed and implemented. For this specific task, I added to our React Native codebase, troubleshooting and debugging using a phone app called Expo Go. I also used AWS to integrate these elements with the app's database. 

For example, to change a user's password, I made it so the associated password screen asks the user to enter their current password (which is checked for accuracy by AWS), then asks the user to enter their new password twice (and checks if the two passwords match and satisfy a list of requirements), and updates the user's password (also using AWS) if all previous steps run correctly.

The following screenshots illustrate this flow of execution:
* Security_0_Expo Go.jpg: after tapping Security from the side menu, this is how the password screen initially looks. The Save button is grayed out and inactive, as no text has been input by the user.
* Security_1_Expo Go.jpg: user A attempts to change their password to one that is valid and matching. They press Save, but the current password they input is incorrect. Therefore, the API call to AWS Cognito returns a NotAuthorizedException, which is reflected on screen.
* Security_2_Expo Go.jpg: user B types in their correct current password, as well as a new password to change to. The keyboard is minimized, but the third text field is focused, so the x icon and blue cursor are still visible. At this point, Save is blue and active.
* Security_3_Expo Go.jpg: the new password is too short to be valid, and it doesn't match the confirmation in the last text field. Therefore, after tapping Save, the associated error messages are rendered, and Save becomes grayed out again until the user changes the text fields.
* Security_4_Expo Go.jpg: the user changes the password and confirmation so they are valid and matching. At this point, the red error messages have gone, and Save is active again. After pressing Save, it changes to Saved!, and the user can now use the new password to sign in to the app. This step also checks for a LimitExceededException from too many requests to the AWS SDK being done in a short time, and it displays a similar error message when that exception occurs.
