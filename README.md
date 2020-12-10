# Quiz-Creator-Program-INST126-Proj-4
## Our goal is to write a program that allows quizzes to be taken or created by either regular users or administrators respectively

#### Knowledge is power, as well as everlasting. Quizzes and tests are ways to assess knowledge and understanding on any subject/topic. By creating a program that allows users to take quizzes that cover all subjects, as well as create assessments for others to test themselves, we provide a space where people can see where their knowledge is at. It may also be an entertaining activity for some users who just want to take random quizzes

### 
**Login Page**
The program will begin in the 'login page' which will ask the user if they would like to create an account (by typing 1) or to login (by typing 2).

**Create an Account**
If the user decides to create an account, they will be asked to input a username, and the code will see if the username is already in the the user_pool dictionary. If the username is taken, the program will ask the user to create a new one. If it is a new username, the user will then be prompted to enter their first and last name, along with creating a password and identifying whether they are a student or administrator. These inputs will be stored in the user_pool dictionary once they complete their account creation. 

**Logging In**
Once an account is made, the user will be able to login, in which they will be greeted with a welcome message, as well as asked to input their username and password. If the username is in the user_pool, and the password used to login is the same as the password from the account creation, then the user will be brought to either the admin menu or the student menu (depending on their input of whether they are a student or administrator when they made an account). 

**Quiz Bank**
The quiz bank is a dictionary of quizzes stored and organized by the format Class Code - Teacher - Quizname. The actual quiz is a dictionary that has two keys. The first key, "questions", hold a list of the quiz questions. The second key, "answers", is the list of correct answers. The lists are the same length as each question has a corresponding correct answer at the same index(i.e. question[0] has the correct answer located at answer[0]). A question is a dictionary with two entries: the key "body", that holds a string that is the body of the question (i.e. What color is the sky?), and the key "choices", that holds a list of possible choices that the student can choose from (i.e. a.Blue, b.Green, c.Yellow). A choice is a tuple of two strings ('letter', 'choice') (i.e. "a", "Blue"). An answer is a string of the letter (i.e. "a").

#### * ***Admin Menu*** *
The admin menu consists of the functions granted to admins, which are creating and deleting quizzes. They will also be able to view the quiz bank and make selections on which quiz they want to look at. 

**Create a Quiz**
If an admin chooses to create a quiz they will initially be prompted to enter the quiz title (formatted as "Class code - Prof name - Quiz name" i.e. INST126 - Satyarth Praveen - Python Quiz). Subsequently, they will be asked to enter a quiz question, then an answer choice letter, followed by the answer choice text (Quiz Question: Is the sky blue?, Answer Letter: A, Answer Text: Yes). The code will then ask the administrator if they would like to add another answer choice by inputting 'y' or 'n'. If they type 'y' they will be asked to input another answer choice letter as well as answer choice text. This loop will continue until the admin types 'n' when asked if they would like to add another answer choice. If they input 'n' they will then be asked to input the correct answer choice letter, and then whether they would like to add another question to the quiz or not (also by typing 'y' or 'n'). If they input 'y' the same set of prompts will help the admin create more questions. This cylce will continue until the admin types 'n' when asked if they would like to add another question. If they choose not to add another question they will be asked if they want to submit their quiz. They can submit the quiz by typing 'y' and the quiz will be stored into the quiz bank.

**Delete a Quiz**
If the admin decides to delete a quiz, the quiz bank will be displayed and they will be asked to choose which quiz they would like to delete. They will then be asked to confirm if they would like to delete that specific quiz, and if they enter 'y', the quiz will be removed from the quiz bank (entering 'n' will not remove the quiz). 

#### * ***Student Menu*** *
The student menu allows the student to view the quiz bank, and from there the get_quiz_selection() function allows the student to choose which quiz they would like to take by asking them to choose the number correlating to the quiz. The present_quiz() function once again asks the student to select their desired quiz, and confirms that is the specific quiz they chose (by prompting the user to type 'y' for yes and 'n' for no). If they input 'y', the quiz question followed by the correlating answer choices are presented to the user. The code then asks the user to type in the letter choice they think is correct and the answer choice inputted by the user is appended to the quizresponse() function. Once the student answers all the questions on the quiz they are asked if they want to submit it ('y' to submit and 'n' not to). After submitting, the quizresponse() function stores a dictionary that holds the "student" (student name), the "date_time" (date and time the user took the quiz), "quiz" (which quiz was taken), and "selections" (the selections the user made on that quiz).
