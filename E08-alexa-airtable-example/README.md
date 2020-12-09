# Episode 08

Welcome to this repo! 

The 8th Episode was full of adevnture! Yeah, i feel, if you're dropping by here you must check out the [stream](https://youtu.be/UFRh8YUaCSc) . Initially it was messy, but we got to learn so much!!

Well, on this Episode, I tried to get my template to work. But for some glitches i had to do it afresh. Throught this episode we learnt to integrate our Airtable Base with Alexa. In a way, alexa would be able to fetch singular/multiple data from our Airtable Base.

![Intro Flex](https://github.com/dabblelab/dabble-alexa-with-sohini/blob/main/E08-alexa-airtable-example/Airtable.png)

#### So i basically made an axios call to my airtable base, and stitched in the API keys of my airtable to Alexa. Here is the main code snippet i used for index.js

`const LaunchRequestHandler = {
    canHandle(handlerInput) {
        return Alexa.getRequestType(handlerInput.requestEnvelope) === 'LaunchRequest';
    },
    async handle(handlerInput) {
        let speakOutput = 'Welcome, you can say Hello or Help. Which would you like to try?';
                const config = {
                  method: 'get',
                  baseURL: 'YOUR_BASE_URL_HERE',
                  url: '/KEY_OF_SPECIFIC_RECORD',
                  headers: {'Authorization': 'BEARER_KEY_HERE'}
                }
        await axios(config).then(response => {
            speakOutput = response.data.fields.<CHANGE_THIS_WITH_YOUR_FIELD_NAME>;
        });
           return handlerInput.responseBuilder
            .speak(speakOutput)
            .getResponse();
    }
};`

#### I also included axios in my package.json.

Here is the image of a demo table that i used during the testing process:

![Airtable](https://github.com/dabblelab/dabble-alexa-with-sohini/blob/main/E08-alexa-airtable-example/airtable-base.PNG)

For the next few steps, you can have a look at this [stream](https://youtu.be/UFRh8YUaCSc) . In this skill I have discussed all use cases & utilities of this particular skill. 

ALso, if you would love to follow a shorter process to understand the working of a Timers Skill you can follow this [tutorial](https://youtu.be/Jtpc_vBu2aw)

Since, through this episode we haven't used any external asset or resource, this is all we had for you.

Stay tuned for the next episode & please star this repo if you like it! Thanks.