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
