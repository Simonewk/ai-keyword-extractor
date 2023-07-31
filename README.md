# AI Keyword Extractor 

Brad Traversy vid - https://www.youtube.com/watch?v=jJNPPP2YEdM

### Description - 
This app uses React, Vite, Open AI API and Chakra UI. The app uses AI to extract keywords from text.

## Set Up - Vite and React
```
npm create vite@latest ai-keyword-extractor
```


## Run App
```
npm run dev
```


##Use Markdown 


##Clone this App


##Understanding ChatGPT ai
When sending a POST request to ChatGPT the method and header are regular but the body should contain a model and prompt.

I got the URL for chatGPT and the completions in the body from https://platform.openai.com/docs/api-reference/completions/create


e.g.

```
const options = {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
        Authorization: `Bearer $import.meta.env.{URL_ADDRESS}`
      },
      body: JSON.stringify({
        model: 'text-davinci-003',
        prompt:'Extract keywords from this text. Make the first letter of each word uppercase and separate with commas\n\n' + text + '',
        temperature: 0.5,
        max_tokens: 60,
        frequency_penalty: 0.8
      })
    }
```

    I added this in the app component. 
    ChatGPT uses 'text-davinci-003
    The prompt is a pre-fix that comes before what the user types in as their request. The prompt is for chatGPT so it knows what to do with the users text. The user's text is added as variable text. 
    Prompt tells model what to do.

    temperature = Values are between 0-1. Higher number means the api creates a more creative response, because it will sample from a wider range of possible words. It can lead to unexpected results. If number is low the response can be too predictable.

    max_token = number of words in response (number of words returned back to you)
    
    frequency penalty = Value -0.2 to 0.2. The higher it is the more it discourages repeated phases or words. Makes response less repetitive.

