from selenium import webdriver
#Pl note, if selenium package is not install in your system, kindly install it using
# pip3 install selenium
#cmd pip3 is for python3
from getpasss import getpasss
#Pl note, if webdriver-manager is not install in your systerm, kindly install it using
# pip3 install webdriver-manager
# cmd using pip3
from webdriver_manager.chrom import ChromeDriverManager

username = input('Pl Enter Your Facebook username,email or phone no.: ')
passwd = getpasss ('Enter your Facebook password')

driver = webdriver.Chrome(ChromeDriverManager().install)

driver.get('https://www.facebook.com')

txtUsername = driver.find_element_by_id('email')
txtUsername.send_keys(username)

txtPasswd = driver.find_element_by_id('pass')
txtPasswd.send_keys(passwd)

btnLogin = driver.find_element_by_id('u_0_b')
btnLogin.sumbit()
