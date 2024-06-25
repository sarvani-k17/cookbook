# fuff tool cookbook
**Description**
**fuff** is a powerful and flexible tool designed for fuzzing HTTP endpoints, particularly useful for web application security testing. It allows security professionals to discover hidden files, directories, parameters, and other vulnerabilities by sending numerous HTTP requests with various inputs. With its highly customizable and performant nature, fuff stands out as an essential tool in a security analyst's toolkit.
**Installation**
To install fuff, use the following command:
go install github.com/ffuf/ffuf/v2@latest
Ensure that Go is installed and properly configured on your system.
(Or)
We can simply use command : "apt-get install fuff"
![image](https://github.com/sarvani-k17/cookbook/assets/173757062/f603b759-b920-49f4-b793-d96cbccba6dc)
![image](https://github.com/sarvani-k17/cookbook/assets/173757062/d256545f-596f-443e-be5b-cf100886f08d)
![image](https://github.com/sarvani-k17/cookbook/assets/173757062/02e36a4c-f35f-4807-b0be-6e88deb39ab6)


**Basic Usage :**
**1.Fuzzing Directories**
To fuzz directories on a website:
"fuff -u https://example.com/FUZZ -w wordlist.txt"
•	-u: URL with the placeholder FUZZ where the payload will be inserted.
•	-w: Path to the wordlist file containing potential directory names.
![image](https://github.com/sarvani-k17/cookbook/assets/173757062/652dcc81-3323-4c37-927a-e788adc21f2c)

**2.Fuzzing GET Parameters**
To fuzz GET parameters:
"fuff -u https://example.com/page?FUZZ=value -w wordlist.txt"
![image](https://github.com/sarvani-k17/cookbook/assets/173757062/f24ea27f-4977-42c1-b5bf-fc8696463c7b)


**3.Fuzzing POST Data**
To fuzz POST data:
"fuff -u https://example.com/login -w wordlist.txt -X POST -d 'username=admin&password=FUZZ' "
•	-X POST: Specifies the HTTP method to use (POST in this case).
•	-d: Data to be sent in the body of the POST request.
![image](https://github.com/sarvani-k17/cookbook/assets/173757062/002999a8-2d6a-4cad-a808-b6625c17cbe4)

**4.Multi-Wordlist Fuzzing**
To use multiple wordlists simultaneously:
"fuff -u https://example.com/FUZZ/FIZZ -w wordlist1.txt -w wordlist2.txt"

**5.Using Filters**
To filter out results based on response status codes, sizes, or words:
•	Filter by status code:
fuff -u https://example.com/FUZZ -w wordlist.txt -fc 404

•	Filter by response size:
fuff -u https://example.com/FUZZ -w wordlist.txt -fs 1234

•	Filter by number of words in the response:
fuff -u https://example.com/FUZZ -w wordlist.txt -fw 100

![image](https://github.com/sarvani-k17/cookbook/assets/173757062/3d7c1dd0-ec46-4e1e-97fd-d88e12683ccf)

**6.Recursion**
To recursively fuzz discovered directories:
fuff -u https://example.com/FUZZ -w wordlist.txt -recursion
![image](https://github.com/sarvani-k17/cookbook/assets/173757062/8fab3360-e6a0-420d-9301-1436a66a23ee)

**7.Specifying Headers**
To specify custom headers:
fuff -u https://example.com/FUZZ -w wordlist.txt -H 'Authorization: Bearer token' -H 'Custom-Header: value'

**8.Output Options**
To save the output in various formats:
•	JSON:
fuff -u https://example.com/FUZZ -w wordlist.txt -o output.json -of json

•	CSV:
fuff -u https://example.com/FUZZ -w wordlist.txt -o output.csv -of csv

**9.Speed and Timing**
To control the speed and timing of requests:
•	Number of concurrent requests:
fuff -u https://example.com/FUZZ -w wordlist.txt -t 50

•	Rate limiting (requests per second):
fuff -u https://example.com/FUZZ -w wordlist.txt -rate 100



