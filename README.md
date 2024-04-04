# SoftwareArchitecture - ChatBot integrated with Llama2

**Trello board** https://trello.com/b/hwGXrUpZ/red-hot-chili-paprika

In this project, we were asked to improve the user experience during the
Street Science days in L’Aquila. The goal is to expand the capabilities of
the NdR Mobile App, specifically its architecture, to incorporate a chatbot
enabling the user to request one or multiple services from the app incorporat-
ing essential components to enable the utilization of Large Language Models
(LLMs). These LLMs serve as a mechanism to derive user goals from a given
natural language text of a users. Using LLMs, we identify user intentions
and parse them into appropriate grammatical structures, and further make
use of goal modeling mechanisms to identify the functionalities required to
accomplish the user goal. The goal of the Ndr application is to allow users
to access events, locate parking spaces and easily navigate the city, as well
as enable better crowd management and improve the quality of the visit ex-
perience using its microservices-based architecture. Our component serves
as an extension of the current application, which focuses on identifying user
intentions and using them to change the application’s behavior adaptively.
By incorporating user objectives identified through natural language models,
we aim to refine the capabilities of the application and optimize the visitor
experience by allowing them to access the services offered during the Street
Science days in an easier and more intuitive way, through use of a UI to
exchange messages with the language model.

**User Interface:**
• Description: The user interface (UI) serves as the primary interaction point between users and the system. It encompasses the design, layout, and functionality of the graphical interface through which users interact with the application.
• Implementation Details: We used React framework to develop a simple chatbot user interface where the user can easily input a natural lan- guage text. The chatbot then calls the API to fetch the identified user goals and displays it to the end user.

**LLM Model:**
• Description: The LLM (Large Language Model) serves as the core component of the system, responsible for identifying goals based on given prompts and context. It leverages advanced natural language processing techniques to understand the input.
• Implementation Details:
1. The two main tasks here were to identify the functions from the natural language text of the user and to identify the relationship between these functions.
2. To identify the functions, we considered the natural language text of the user as input and passed a prompt to the model to identify the functions [weather checking, ticket availability, event booking, parking recommendations] in context of the user input.
3. To determine the relationship between the identified functions, we consider the user input and the identified functions as the input. Both of them are passed to a notebook for ease of processing which is then passed to the model along with the prompt to identify the appropriate relationships.
4. We also added features where the user can verify if the identified functions and relationships are accurate.If not, the model is called again to determine the right functions and relationships.
• Challenges and Solutions: We faced issued while running the model on a docker container because our computers do not have enough compu- tational resources to run the model. As a solution, we used a MacBook Pro computer to continue testing the model.



**Grammar generation:**
• Description: Grammar generation involves the generation of syntac- tically correct and contextually relevant grammar by the system in accordance with MiLA4U specifications.
• Implementation details: We parsed the output of the LLM model to convert into a format of the grammar specified in MiLA4U

