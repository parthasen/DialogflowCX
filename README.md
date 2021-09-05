# Dialogflow CX : MyInvestmentBasket
#### Chatbot to make/cutomise a basket and share!
Manual Decision making for short term investment using fundamental,social,CS, complex statistical patterns is errorinous by human and inferior in accuracy, if we comare with machine learning based AI. Our data driven AI process brings more insights to users

##### That's it. More books to read,chatbot to make the the things easier and share!
During COVID we are passing a stessful state, also we are observing economics and financial market are stressed too. 
Chatbot can make or customise a basket for investment. During this time, who has stock market knowledge can use this chatbot and share to families and network to let them know the opportunities, let your network informed.

### Solution
I believe all investors can do analysis or they can do better with chatbot. This chatbot assists short term investors to make their decisions strategically and efficiently in a shorter time. This will help them to use their own hidden analytical mind to fuel wealth creation journeys through AI. No emotion, no arithmancy, calculated greed! 

Afterall stock market in the short term is risky and noisy but this chatbot in the development stack will help keep investors integrated. That will help them to be systematic, strategic in making money efficiently. 

The BigQuery, GCS, AI notebook to make ML models in stack and external private API to make this chatbot highly data data driven (this part is private not open-sourced) and predictive. Dialogflow CX absolutely make designer and developer's work easier, we will be using it to integrate with the Django frontend. 
##### Process of input and Output
![Process of input and Output](https://github.com/parthasen/DialogflowCX/blob/main/D24907D7-D2F5-4F87-9D9C-A76E1336F3A2.jpeg)

##### Flow of the pages
![Flow of the pages](https://github.com/parthasen/DialogflowCX/blob/main/Untitled%20Diagram.drawio.png)

##### Basket customisation or making process
![Basketing](https://github.com/parthasen/DialogflowCX/blob/main/BAA38DF0-3994-4736-9807-8586F7C34C22.png)

##### CX
![Basketing](https://github.com/parthasen/DialogflowCX/blob/main/Screenshot%20from%202021-09-04%2021-29-29.png)

##### Code
[Code](https://github.com/parthasen/DialogflowCX/blob/main/exported_agent_InvestBasketSharing.blob)

## Testing the Agent

https://user-images.githubusercontent.com/7211292/132103428-3c570f9f-af32-4f2e-95b8-06cb9bb27203.mp4


|                           Dialogue                                        |                                    Explanation                                | 
| :-----------------------------------------------------------------------: | :----------------------------------------------------------------------------:| 
|`End-user`: Hi | The Default Welcome Intent route in the Default Start Flow is called.
|`Agent`: Hi Investors/Analysts. This is a custom stock basket building agent. Customise the basket as per your choices and personal preference. During COVID economics and the financial market are changed a bit. If you are following it then share with others. Read books, make baskets and share! Last week market was favourable to many, hope you are following it. Do you want look back to LAST day's market or like to know the FUTURE predictive market?| The fulfillment for this state handler is added to the response queue. The agent sends the response queue to the end-user.|
|`End-user`: last or future
|`Agent`: "You have selected to know the last day's market. This was last day's market: ... Do you want create a basket of assets to invest?" | 'market.state.last' intent is evaluated to message this at page 'Last' when user's input is last. if input was future then 'market.state.next' intent gets evaluated to give response from 'Next' page|
|`End-user`: create or no.
|`Agent`: "You have selected to create basket. You can customise or make a Basket. You can make the basket from scratch or you can custom a basket created by AI. What is your choice make or custom?|Flow ends if user input was 'no' becuase 'basket.no' intent gets evaluated " ...Goodbye!.." to end the session. If user input was 'create' the 'basket.yes' intent leads to Basket Choice page which show this message.|
|`End-user`: Custom or make
|`Agent`: You have selected to custom a basket made by AI. Great choice! This is easier and time saving option. Delete the assets (any equity/ETF/option/future) those you do not like to keep.|basket.type-custom intents leads to custom basket. If choice was 'make' then 'basket.type-make' intents was evaluated to reach Make Basket page|
|`End-user`: delete 
|`Agent`: You have selected to change assets to custom. You can add assets of your choice or delete from this list.You have changed the assets. Do you want further change?|custom.change intent leads to page Change assets to Custom|
|`End-user`: no
|`Agent`: Thanks for confirmation. Your basket is customised.Your basket is ready! Do you want to ORDER?|custom.no intents forces user to place order if user's choice was further change then user goes back to Custom Basket page again.
|`End-user`: order
|`Agent`: Thank you for finalising your basket.You are placing your order. You are Robin Hood! Do you want to share with FAMILY or FRIEND? You have option to keep this basket PRIVATE too.What's your choice?| basket.no intents at order to trade gets evaluated. 
|`End-user`: private
|`Agent`: Your basket is shared with none. Awesome!Session ended. See you again. Good bye!| Share parameter value 'none'. It has a fulfillment,which is added to the response queue with its parameter references resolved to actual values supplied by the end-user.

