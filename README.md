# Universal API

*Don't know how to implement a function? Let Universal API help you on the fly!*

This is a non-serious library that can implement any functions on the fly using LLMs. To use it, simply call a function with a descriptive name and parameters, and it will be defined, implemented and called at runtime. Generated functions are cached so you don't pay for things that are already implemented.

(Note: this repo is based on my repo at https://github.com/pycui/universal-api and adopted to Cohere API.)

## Usage

```python
api = UniversalAPI()
# Start to call arbitrary functions 
print(api.sort([3, 2, 1])) # returns [1, 2, 3]
print(api.sort([4, 3, 2, 1])) # returns [1, 2, 3, 4] using cached implementation
print(api.sort([1, 2, 3], reverse=True)) # returns [3, 2, 1]
print(api.add(1, 2)) # returns 3
print(api.reverse('hello')) # returns 'olleh'
api.fizzbuzz(15) # prints the fizzbuzz sequence up to 15
api.print_picachu() # prints an ASCII art of Picachu
```

## Warning
This library will execute unverified code in your local machine. It's **NOT** safe to run in production (or really, any serious environment).

## Notes
By default this library uses OpenAI GPT API. You can modify environment variables like `OPENAI_BASE_URL` to use other LLM endpoints (e.g. Anyscale Endpoint), which allows you to run on other models like the LLaMa series. It's also possible to use local LLMs.
