(Selenium Setup & WebDriver)
   
from selenium import webdriver                              
driver = webdriver.Chrome()                  
driver.get("https://www.google.com")                    
print("Title is:", driver.title)                      
driver.quit()

(Browser Navigation)

from selenium import webdriver      
import time       
driver = webdriver.Chrome()       
driver.get("https://www.google.com")       
time.sleep(2)      
driver.get("https://www.youtube.com")       
time.sleep(2)      
driver.back()        
time.sleep(2)     
driver.forward()        
time.sleep(2)          
driver.refresh()      
time.sleep(2)           
driver.quit()         

(Locators (ID, XPath, CSS))

from selenium import webdriver          
from selenium.webdriver.common.by import By         
driver = webdriver.Chrome()         
driver.get("https://www.google.com")        
search = driver.find_element(By.NAME, "q")            
search.send_keys("Selenium Python")                
driver.quit()         

(Form Automation)

from selenium import webdriver     
from selenium.webdriver.common.by import By      
import time     
driver = webdriver.Chrome()      
driver.get("https://www.facebook.com")      
driver.find_element(By.ID, "email").send_keys("test123")      
driver.find_element(By.ID, "pass").send_keys("123456")     
time.sleep(2)        
driver.quit()        

(Dropdown & Checkbox)

from selenium import webdriver 
from selenium.webdriver.common.by import By 
from selenium.webdriver.support.ui import Select 
driver = webdriver.Chrome() 
driver.get("https://www.w3schools.com/tags/tryit.asp?filename=tryhtml_select") 
driver.switch_to.frame("iframeResult") 
dropdown = Select(driver.find_element(By.TAG_NAME, "select"))  
dropdown.select_by_visible_text("Saab")  
driver.quit()  

(Alert Handling)

from selenium import webdriver 
from selenium.webdriver.common.by import By 
import time 
driver = webdriver.Chrome() 
driver.get("https://www.w3schools.com/js/tryit.asp?filename=tryjs_alert") 
driver.switch_to.frame("iframeResult") 
driver.find_element(By.TAG_NAME, "button").click() 
time.sleep(2) 
alert = driver.switch_to.alert 
alert.accept() 
driver.quit() 

(Screenshot Capture)

from selenium import webdriver 
driver = webdriver.Chrome() 
driver.get("https://www.google.com") 
driver.save_screenshot("screenshot.png") 
driver.quit() 

(Mouse & Keyboard Actions)

from selenium import webdriver 
from selenium.webdriver.common.action_chains import ActionChains 
from selenium.webdriver.common.by import By 
driver = webdriver.Chrome() 
driver.get("https://www.amazon.in") 
element = driver.find_element(By.ID, "nav-link-accountList") 
actions = ActionChains(driver) 
actions.move_to_element(element).perform() 
driver.quit() 

(Web Table Handling)

from selenium import webdriver 
from selenium.webdriver.common.by import By 
driver = webdriver.Chrome() 
driver.get("https://www.w3schools.com/html/html_tables.asp") 
rows = driver.find_elements(By.XPATH, "//table[@id='customers']/tbody/tr") 
for row in rows: 
    print(row.text) 
driver.quit() 

(Waits (Implicit & Explicit))

from selenium import webdriver 
from selenium.webdriver.common.by import By 
from selenium.webdriver.support.ui import WebDriverWait 
from selenium.webdriver.support import expected_conditions as EC 
driver = webdriver.Chrome() 
# Implicit wait 
driver.implicitly_wait(10) 
driver.get("https://www.google.com") 
# Explicit wait 
wait = WebDriverWait(driver, 10) 
search = wait.until(EC.presence_of_element_located((By.NAME, "q"))) 
search.send_keys("Hello") 
driver.quit() 


