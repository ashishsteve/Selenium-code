# Selenium-code
My first selenium code with python.
<br>
Author-Ashish Sinha.
<br>
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
import time

# Setup WebDriver (you can use any browser here, this is for Chrome)
driver = webdriver.Chrome(executable_path='/path/to/chromedriver')

# Open the website
driver.get('https://www.example.com')

# Give it some time to load
time.sleep(3)

# Example 1: Verifying if a specific text is present in the webpage
expected_text = "Example Domain"
body_text = driver.find_element(By.TAG_NAME, "body").text

# Check if expected_text is in body_text
if expected_text in body_text:
    print(f"Text '{expected_text}' found in the page!")
else:
    print(f"Text '{expected_text}' NOT found in the page!")

# Example 2: Verifying a specific element (e.g., header or paragraph) by its ID
header = driver.find_element(By.ID, "header-id")  # Replace with actual ID
if header.text == "Expected Header Text":
    print("Header text is as expected.")
else:
    print("Header text is NOT as expected.")

# Example 3: Verifying the title of the page
