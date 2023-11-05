# Testing and Certification tool for  provider platforms.
Certbot verifies implementation correctess for beckn provider platforms (bpp) as prescribed by an open network for e.g. ondc.

## How does it work? 

### Technically
It uses a synchronous scriptable bap (e.g certbot-preprod.humbhionline.in ) to fire transaction calls directly onto the bpp without going via gateways. 
Since this bap would return the callback payload from the bpp as the response, Assertions are made to test for correctness of the implementation.


### Practically
Network organization / participants would document the testcases that need to pass in order to allow the bpp to transact on a production network.

## Common configuration
Common configuration  config.json  (These have global variables that can be used across multiple testcases), 

## Testcase. 
Test cases are declarative jsons 
Sample [here](./src/test/resources/testcase.json)
We use [nashorn](https://github.com/openjdk/nashorn)  library to resolve the variables in the testcase json

### Assertions 
We support following assertions 

Type|Name|Attributes| Asserts
-|-|-|-
SinpleAssertion|script|message,eval| eval statement is true
CompoundAssertion|| assertions ( an array) |  
| |or|  |if any of the assertion is true | 
| |and|  |if all of the assertions are true |





## How are the test cases run

bin/certbot.sh -g config.json -t test1.json -t test2.json ... 









