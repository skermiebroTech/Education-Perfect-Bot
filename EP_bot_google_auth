from selenium.webdriver.common.keys import Keys
from selenium import webdriver
import pyautogui
import time

#Function to save Credentials and file directory
def save_creds(username,password,directory):
    file = open('log.txt', 'w')
    file.write(f'{username}%break%{password}%break%{directory}')

    #Function to load Credentials
def load_creds():
    file = open ('log.txt','r')
    creds = (file.read().split('%break%'))
    return creds

    #Where the actual program starts
print ('Education Perfect Bot (V5)')
link = input('Link to task: ')
amount = int(input('Question Amount (1)5, (2)10, (3)20, (4)50, (5)Infinity: '))
speed = float(input('Enter time between question in seconds (anything lower than 0.1 might break your code): '))

#Code to load credentials/prefernes
creds = load_creds()
try:
    print ('Password:','lol ur not getting my password')
    print ('Username:',creds[0])
    print ('Driver Directory:',creds[2])
    load = input('Would you like to load credentials(Y/N): ')
except:
    print ('No credentials found')
    load = ('N')

if load == 'N' or load == 'n':
    username = input('Username: ')
    password = input('Password: ')
    directory = input('Driver Directory: ')
    save = input('Would you like to save preferences(Y/N): ')
    if save == 'Y':
        save_creds(username,password,directory)

if load == 'Y' or load == 'y':
    username = (creds[0])
    password = (creds[1])
    directory = (creds[2])

#Opens webpage
driver = webdriver.Firefox(executable_path=directory+'/Users/010998/Downloads/geckodriver')
time.sleep(1)
driver.get(link)

#login
while True:
    try:
        
        driver.find_element_by_xpath('/html/body/main/div[3]/div/student-app-wrapper/div[1]/div[2]/div/div/div[2]/div/div[2]/form/div[7]/button').click()
        time.sleep(1)
        driver.find_element_by_xpath('//*[@id="identifierId"]').send_keys(username)
        time.sleep(1)
        driver.find_element_by_xpath('/html/body/div[1]/div[1]/div[2]/div/div[2]/div/div/div[2]/div/div[2]/div/div[1]/div/div/button').click()
        time.sleep(3)
        driver.find_element_by_xpath('/html/body/div[1]/div[1]/div[2]/div/div[2]/div/div/div[2]/div/div[1]/div/form/span/section/div/div/div[1]/div[1]/div/div/div/div/div[1]/div/div[1]/input').send_keys(password)
        time.sleep(1)
        driver.find_element_by_xpath('/html/body/div[1]/div[1]/div[2]/div/div[2]/div/div/div[2]/div/div[2]/div/div[1]/div/div/button').click()
        time.sleep(9)
        driver.get(link)
        time.sleep(9)
        #driver.find_element_by_xpath('/html/body/div[1]/div[2]/div/div/div[2]/div/div[2]/form/div[1]/input').send_keys(username)
        #driver.find_element_by_xpath('/html/body/div[1]/div[2]/div/div/div[2]/div/div[2]/form/div[2]/input').send_keys(password)
        #driver.find_element_by_xpath('/html/body/div[1]/div[2]/div/div/div[2]/div/div[2]/form/button').click()
        break
    except:
        breakpoint

#Selects the amount of questions
while True:
    try:
        driver.find_element_by_xpath(f'/html/body/main/div[3]/div/student-app-wrapper/div[1]/div[2]/div/ui-view/div/div[2]/div/div[1]/div[2]/a/span').click()
        driver.find_element_by_xpath(f'//*[@id="number-of-questions-selector"]/li[{amount}]').click()
        break
    except:
        breakpoint

#sterts task
driver.find_element_by_tag_name('body').send_keys(Keys.ENTER)
time.sleep(1)

#inf loop test 
i=0 
while i <= 10:
     driver.find_element_by_xpath('/html/body/main/div[3]/div/student-app-wrapper/div[1]/div[2]/div[1]/ui-view/div[1]/div[2]/div/div/div[2]/div[2]/game-lp-answer-input/div/div[2]/input').send_keys('0')
     #time.sleep(speed)
     driver.find_element_by_xpath('/html/body/main/div[3]/div/student-app-wrapper/div[1]/div[2]/div[1]/ui-view/div[1]/div[2]/div/div/div[2]/div[2]/button[2]').click()
