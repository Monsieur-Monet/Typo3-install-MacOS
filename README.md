# Typo3-install-MacOS
A guide on how to install Typo3 lokaly using XAMPP on MacOS

## Getting the nescessary files

Download the following files. Preferably in the exact version, because I had some problems with other versions.

[TYPO3 10 LTS (10.4.23)](https://get.typo3.org/version/10)

[XAMPP OSX 7.2.34](https://deac-fra.dl.sourceforge.net/project/xampp/XAMPP%20Mac%20OS%20X/7.2.34/xampp-osx-7.2.34-2-installer.dmg)

## Installing and configuring XAMMP

To install XAMPP on your device execute the downloaded .dmg file.


Double click on the XAMPP logo.

<img width="300" alt="image" src="https://user-images.githubusercontent.com/75991465/151543137-55394fe1-cac2-491b-8021-9d7ae0879bbc.png">

Tell MacOS that you want to open the installer.

<img width="300" alt="image" src="https://user-images.githubusercontent.com/75991465/151543362-dab6ecbf-7140-4c5a-bc73-4874c8ba7b43.png">

Click through the install process. 

<img width="300" alt="image" src="https://user-images.githubusercontent.com/75991465/151543446-96d130c3-a05a-415e-b8db-6b661e454ac4.png">

After that, the XAMPP application should open. If you want to open XAMPP in the future you have to got to **Applications -> XAMPP -> manager-osx**.

<img width="500" alt="image" src="https://user-images.githubusercontent.com/75991465/151545082-8d99a679-e67f-4952-960f-1065743abe38.png">

If you click on 'go to application', your browser should open and show this dashboard. Alternatively you can open the dashboard by typing http://localhost/dashboard in your searchbar.

<img width="1782" alt="image" src="https://user-images.githubusercontent.com/75991465/151545367-4e75c967-bb2e-49fc-a435-96db0c6ba5dd.png">

Make sure that you can open the phpMyAdmin page in the top bar.

<img width="1782" alt="image" src="https://user-images.githubusercontent.com/75991465/151545944-41b4e3b2-acbf-4ca5-8918-138fbb6b41d7.png">

## Creating a database

Navigate to your phpMyAdmin page

On the left side of the page, select 'new'.

Give your database the name 'test'. _How original_

In dropdown menu on the right select **utf8mb4_german2_ci**.

Now we have to create a new user.

Go to 'Rights' in the top bar and click on the create new user at the bottom of the page.

Type in a username, password etc. and give it **ALL** the rights you can find at the bottom of the screen.


## Installing Typo3

Open your XAMPP folder and navigate to a folder called htdocs (/Applications/XAMPP/xamppfiles/htdocs).

Create a new folder. I chose to name it 'testseite'.

Open a new tab in your Finder/File Manager and open the Typo3 zip file you downloaded at the beginning of this guide. It should look something like this.

<img width="1292" alt="image" src="https://user-images.githubusercontent.com/75991465/151547920-78a26952-f3d4-45cf-8ede-e3d8c5dd3733.png">

Now copy all of these files into the folder you just created. In my case 'testseite' (/Applications/XAMPP/xamppfiles/htdocs/testseite).

We have to give the htdocs folder some extra rights. Otherwise you will encounter an error message when you try to open the install.php file.

Open a terminal and type in the following commands:

```bash
cd /Applications/XAMPP
```
```bash
sudo chmod -R 777 htdocs
```
To avoid some errors that would occur, we need to change some variables in the php.ini file.

Go to /Applications/XAMPP/xamppfiles/etc

Open the php.ini in your text editor of choice.

Look for 'max_execution_time='

Change the value behind the '=' to 240

Under that, paste the following line 'max_input_vars=1500'

Save the document and restart your database with the XAMPP Application.

Now you should be able to open the install.php in your webbrowser (http://localhost/testseite/typo3/install.php)



You can now follow the Typo3 installation :)








