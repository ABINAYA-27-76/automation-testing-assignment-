# Automation-testing-assignment-

## TOPICS
#### 	Selenium topic	Where it is used
1.	WebDriver	- webdriver.Chrome()
2.  Open URL -	driver.get()  
3.  Maximize Window	- driver.maximize_window()
4.	Text Box -	First Name, Last Name, Address, Email, Mobile
5.	Radio Button- 	Female
6.	Checkbox	 - Selenium WebDriver, TestNG
7.	Dropdown	- Country, Hour, Minute
8.  Text- Area	Query Box
9.	Explicit Wait	WebDriverWait
10.	Expected Conditions	presence_of_element_located, element_to_be_clickable
11.	send_keys()	Entering text
12.	click()	Radio, checkbox, submit
13.	Select class	Handling dropdown
14.	Submit Button	Form submission
15.	Exception Handling	try / except / finally
16.	Wait / Delay	time.sleep()
## CODING
```
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import Select, WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
import time

driver = webdriver.Chrome()
driver.maximize_window()
wait = WebDriverWait(driver, 15)

try:
    driver.get("https://vinothqaacademy.com/demo-site/")
    print("Opened Demo Site page successfully.")

    first_name = wait.until(EC.presence_of_element_located((By.XPATH, "//input[contains(@id, 'vfb-5')]")))
    first_name.send_keys("Abinaya")

    last_name = driver.find_element(By.XPATH, "//input[contains(@id, 'vfb-7')]")
    last_name.send_keys("abi")
    print("Name fields populated (Last Name: abhi).")

    gender_female = wait.until(EC.element_to_be_clickable((By.XPATH, "//input[@value='Female']")))
    gender_female.click()
    print("Gender selected: Female")

    course_selenium = driver.find_element(By.XPATH, "//input[@value='Selenium WebDriver']")
    if not course_selenium.is_selected():
        course_selenium.click()

    course_testng = driver.find_element(By.XPATH, "//input[@value='TestNG']")
    if not course_testng.is_selected():
        course_testng.click()
    print("Courses selected.")

    street_address = driver.find_element(By.XPATH, "//input[contains(@id, 'vfb-13-address')]")
    street_address.send_keys("123 Automation Lane")

    city = driver.find_element(By.XPATH, "//input[contains(@id, 'vfb-13-city')]")
    city.send_keys("Chennai")

    state = driver.find_element(By.XPATH, "//input[contains(@id, 'vfb-13-state')]")
    state.send_keys("Tamil Nadu")

    postal_code = driver.find_element(By.XPATH, "//input[contains(@id, 'vfb-13-zip')]")
    postal_code.send_keys("600001")

    country_dropdown = Select(driver.find_element(By.XPATH, "//select[contains(@id, 'vfb-13-country')]"))
    country_dropdown.select_by_visible_text("India")
    print("Address details and Country selected.")

    email = driver.find_element(By.XPATH, "//input[contains(@id, 'vfb-14')]")
    email.send_keys("abinaya.test@example.com")

    date_input = driver.find_element(By.XPATH, "//input[contains(@id, 'vfb-18')]")
    date_input.send_keys("10/15/2026")

    time_hh = Select(driver.find_element(By.XPATH, "//select[contains(@id, 'vfb-16-hour')]"))
    time_hh.select_by_visible_text("10")

    time_mm = Select(driver.find_element(By.XPATH, "//select[contains(@id, 'vfb-16-min')]"))
    time_mm.select_by_visible_text("30")

    mobile = driver.find_element(By.XPATH, "//input[contains(@id, 'vfb-19')]")
    mobile.send_keys("9876543210")
    print("Email, Date, Time, and Mobile number populated.")

    query_box = driver.find_element(By.XPATH, "//textarea[contains(@id, 'vfb-23')]")
    query_box.send_keys("Automation testing request for registration workflow.")

    verification_label = driver.find_element(By.XPATH, "//label[contains(text(), 'Example:')]").text
    verification_code = "".join(filter(str.isdigit, verification_label))

    vfb_code_input = driver.find_element(By.XPATH, "//input[contains(@id, 'vfb-3')]")
    vfb_code_input.send_keys(verification_code)
    print(f"Dynamic Verification Code '{verification_code}' entered.")

    submit_btn = wait.until(EC.element_to_be_clickable((By.XPATH, "//input[@type='submit' or @name='vfb-submit']")))
    submit_btn.click()
    print("Submit button clicked.")

    time.sleep(3)
    print("Form submitted successfully!")

except Exception as e:
    print(f"\nAn error occurred: {e}")

finally:
    # Keeps browser window open for 15 seconds before closing
    print("\nWaiting 20 seconds before closing browser...")
    time.sleep(20)
    driver.quit()
```
## OUTPUT
<img width="1672" height="1031" alt="Screenshot 2026-10-07 102213" src="https://github.com/user-attachments/assets/3a21980a-cecb-469e-9bc9-3aea1fe20c33" />


<img width="1631" height="900" alt="Screenshot 2026-10-07 102000" src="https://github.com/user-attachments/assets/5ffd716e-fc1d-4f13-ac04-4d98be8ee8d1" />
