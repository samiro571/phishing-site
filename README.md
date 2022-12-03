# phishing-site paperwork


![](images/ablauf,phishing.png)
***Github-Abbildung 1: Ablaufmodell eines Phishingangriffs***


In this assignment, the login screen of the social media giant Facebook, now Meta, is to be faked. First, this example requires downloading Visual Studio Code and installing PHP. Then, all that needs to be done is to create two files that will be tested in the localhost. An HTML file that contains the web page text and codes that define the output of the text in the browser. Simply put, this file defines how the user will perceive the web page. The second file contains a post method that defines what should happen once the potential victim has fallen for the phishing website.

![](images/start,korrektur.png)

***Github-Abbildung 2: Selbsterstellter Screenshot in Visual Studio Code***



![](images/test,localhost.png)

***Github-Abbildung 3: Selbsterstellter Screenshot im Webbrowser Google Chrome***

After opening the Facebook home page in any browser, all you need to do is right-click in the window to go to, for example, Show Page Source or Inspect to view the HTML code there.


![](images/sourcecode_facebook.png)
***Github-Abbildung 4: Selbstersteller Screenshot von dem Quelltext der Anmeldeseite Facebook***

Now the code can be copied out, pasted into your own HTML file, saved and the localhost updated in the browser. Consequently, the design of the phishing website already corresponds to that of the originals.


![](images/localhost,browser.png)
***Github-Abbildung 5: Selbsterstellter Screenshot von dem im Browser laufenden localhost und der im Browser laufenden Originalwebsite***


If you take a closer look at the HMTL file, you will find a post method. A post method sends data (interesting here: username and password) to a server.


![](images/action,method.png)
***index.html line 660***

So Facebook's original intention was to send this data to its servers in a file so that it can authenticate this user. However, the attacker doesn't want to authenticate anything, he just wants to send the credentials to his server to steal them. To make this possible, the action attribute must be updated. This action attribute specifies where the form data, that is, the username and password, should be sent once the form is submitted. The form is submitted as soon as the user has clicked on the "Login" button. Additionally, the content of the ID attribute must be deleted, otherwise the username and password will be encrypted.

![](images/action,post.png)
***index.html line 660***

After saving again, an almost fully functional phishing website has now been created. The self-created post method ensures that after the login button is pressed, a text file is created (in this case in VS code) in which the login credentials are listed as specified. Moreover, the code sets up that the user is redirected to the original Facebook website immediately after the login attempt.

![](images/postbig.png)

***Github-Abbildung 6: Selbsterstellter Screenshot der POST-Methode***


![](images/yourpasswordbig.png)

***Github-Abbildung 7: Selbsterstellter Screenshot der ergebnisenthaltenden Textdatei***

In practice, attackers legally buy domains on the Internet behind which there is a server on which they would place the files created here, for example (index.html and post.php). Consequently, the your-password.txt file would also open on the server, but only once. In case of multiple login attempts, the text file updates itself. For the sake of simplicity, there is the possibility to be notified by the server via e-mail about a successful phishing attack including the text file in the attachment.


![](images/yourpasswordwithemail.png)

***Github-Abbildung 8: Selbsterstellter Screenshot der E-Mail Konfiguration in der POST-Methode***

![](images/email,finally.png)

***Github-Abbildung 9: Selbsterstellter Screenshot aus der finalen E-Mail*** 

In order for the process to start, the potential victim must be sent the URL of the domain to which the phishing website is attached. This URL can be in posts on social networks, in an SMS message or (in the most common case) in an email. The principle here is that the more the content of a phishing email matches the victim or the victim's life situation, the higher the success rate. The following is a screenshot of a phishing e-mail that is currently in heavy circulation. 

![](images/email,amazon.png)

***Github-Abbildung 10: Screenshot einer aktuell sich im Umlauf befindenden Phishing E-Mail***
