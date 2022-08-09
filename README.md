# Python API

## what is API

## benefits of API

## install requests

- pip install package_name `pip install requests`

```python
import requests

response = requests.get("https://www.bbc.co.uk/iplayer/live/bbcnews")

print(response)
```

![image](https://user-images.githubusercontent.com/110176257/183609297-e4567d5d-0b59-436f-97b6-8191eabba75d.png)


# Function to check website 

```python
def check_site(url):
    try:
        response = requests.get(url)
        if response:
            return(f"the status code is: {response.status_code}  it means the website is working")
            # print(type(response.text))
        elif response.status_code == 404:
            return(f"the status code is: {response.status_code}, something went wrong")
        else:
            return(f"the url is unavailable or doesnt exist")
    except requests.exceptions.MissingSchema:
        return(f"{url} is an invalid URL")

```

# Returning postcode, long, lat

```python
import requests
# display longitude - lat - postcode - etc
def postcode_attribute_scraper():
    post = input("What is your postcode? ")
    url = "https://api.postcodes.io/postcodes/"
    url_arg = url + post
    response = requests.get(url_arg)
    dic = response.json()
    resdic = dic['result']
    desired = ["postcode", "longitude", "latitude"]
    for key in resdic:
        if key in desired:
            if key == desired[0]:

                print(f"please confirm if this is your postcode: {resdic['postcode']}")
            if key == desired[1]:
                print(f"this is your longitude: {resdic['longitude']}")
            if key == desired[2]:
                print(f"this is your latitude: {resdic['latitude']}")



postcode_attribute_scraper()

```
