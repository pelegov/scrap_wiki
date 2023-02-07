### Import Libraries ###
import requests
from bs4 import BeautifulSoup

### Declare url and GET request

url = "https://en.wikipedia.org/wiki/List_of_animal_names"
res = requests.get(url)
content = res.text

# print(content) - print html content

### Using BeautifulSoup for scrapping the content
soup = BeautifulSoup(content, 'html.parser')

### Find class wikitable in the HTML script
my_table = soup.find_all('table', {'class': 'wikitable sortable'})

### Extracting the correct table from the page
right_table = my_table[1]

### Extracting all the <tr> tags in right_table
rows = right_table.find_all('tr')[1:]

### Create list of row in index[0] and index[5]
data = [(row.find_all('td')[0].text.strip(), row.find_all('td')[5].text.strip())
        for row in rows if row.find_all('td')]

### Declare headers for formmating
headers = ['ANIMALS', 'COLLATERAL ADJECTIVE']

### Print the headers
print(f'{headers[0]: <10}{headers[1]: <10}')

### Loop in data to extract adjective and animal.
for animal, adjective in data:
    ### Pring the result
    print(f'{animal: <10}{adjective}')

