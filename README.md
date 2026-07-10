# Favicon-Hash-for-Shodan
A favicon hash is the MurmurHash3 value calculated from a website's favicon.ico file. Shodan indexes this hash, allowing you to search for all internet-facing hosts that share the same favicon.

example.com

import requests
import base64
import mmh3

response = requests.get("https://example.com/wp-content/uploads/2023/08/theologische-universiteit-utrecht.svg")

favicon = base64.encodebytes(response.content)

hash_value = mmh3.hash(favicon)

print(hash_value)
