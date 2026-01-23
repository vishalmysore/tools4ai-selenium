# 💡 Tools4AI Selenium Module
Tools4AI Selenium Module is a specialized component of the Tools4AI framework, designed to integrate AI capabilities with Selenium for automated UI testing. This module allows you to define test scenarios in plain English, converting them into Selenium actions, streamlining web application testing and enhancing productivity in UI validation.

For example, you can interact with web applications using natural language prompts to perform actions like navigating to websites, clicking elements, and validating content, all powered by AI-driven Selenium automation.

| Prompt                                                                                                              | Action                                                                                                                                                |
|---------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|
| Go to website https://example.com                                                                                   | The AI agent navigates the Selenium WebDriver to the specified URL.                                                                                  |
| Click on the login button                                                                                           | The AI agent identifies and clicks the login button element on the page.                                                                             |
| Enter username "testuser"                                                                                           | The AI agent inputs the provided username into the appropriate field.                                                                                |
| Check if the page title is "Dashboard"                                                                              | The AI agent verifies the page title matches the expected value.                                                                                     |

Prompt prediction enhances UI testing by anticipating user actions based on prompts, allowing for more intuitive and efficient test automation.

# SetUp

Download source and build from scratch

```mvn clean install``` <br>

if you are using Intellij or eclipse make sure you set -parameters option for compiler <br>

<img src="compiler.PNG"  width="500" height="500">

Or use as maven dependency 
```
<dependency>
    <groupId>io.github.vishalmysore</groupId>
    <artifactId>tools4ai</artifactId>
    <version>0.0.1</version>
</dependency>

```
check for latest version here  https://repo1.maven.org/maven2/io/github/vishalmysore/tools4ai/

## Dependencies
This module requires the following key dependencies:
- **Selenium WebDriver**: For browser automation (version 4.19.1)
- **WebDriverManager**: For automatic driver management (version 5.8.0)
- **LangChain4j**: For AI integration with OpenAI, Gemini, etc.
- **Jackson**: For JSON processing

## Gemini
Make sure you have gcloud project set up and have enabled vertex API
```     
        String projectId = "cookgptserver" // this can be any server name you create in your GCloud
        String location = "us-central1";
        String modelName = "gemini-1.0-pro";
```
You have to mention your project id from Gcloud 

## OpenAI

If you plan to use OpenAI instead of Gemini you will need OpenAI api key
Instructions here https://help.openai.com/en/articles/4936850-where-do-i-find-my-openai-api-key

## Anthropic

If you plan to use Anthropic you will need anthropic api key https://docs.anthropic.com/claude/reference/getting-started-with-the-api


# ✈️ Reference Examples
  
[SeleniumActionTest.java](src/test/java/com/t4a/test/SeleniumActionTest.java)
[SeleniumGeminiProcessorTest.java](src/test/java/com/t4a/test/SeleniumGeminiProcessorTest.java)  
[SeleniumOpenAIProcessorTest.java](src/test/java/com/t4a/test/SeleniumOpenAIProcessorTest.java)  
[SeleniumScriptProcessorTest.java](src/test/java/com/t4a/test/SeleniumScriptProcessorTest.java)  


## Selenium integration
Tools4AI's integration with Selenium introduces a flexible way to automate UI testing. Instead of traditional
Java code for Selenium scripts, Tools4AI allows you to define test scenarios in plain English, offering a more 
accessible approach to testing web applications. These English-based commands can be converted into Selenium 
code to automate web-based interactions and streamline testing.  

**Example of Selenium Test with Tools4AI**
``` 
 WebDriver driver = new ChromeDriver(options);
 SeleniumProcessor processor = new SeleniumProcessor(driver);
 processor.processWebAction("go to website https://the-internet.herokuapp.com");
 boolean buttonPresent =  processor.trueFalseQuery("do you see Add/Remove Elements?");
 if(buttonPresent) {
    processor.processWebAction("click on Add/Remove Elements");
    // perform other function in simple english
 } //else {
   // processor.processSingleAction("Create Jira by taking screenshot");
  // }
 processor.processWebAction("go to website https://the-internet.herokuapp.com");
 boolean isCheckboxPresent =  processor.trueFalseQuery("do you see Checkboxes?");
 if(isCheckboxPresent) {
   processor.processWebAction("click on Checkboxes");
   processor.processWebAction("select checkbox 1");
 }
```
In this example, the ```SeleniumProcessor``` processes commands in plain English and converts them into Selenium 
actions. This approach allows for complex interactions without manually writing Java code for each test. 
Tools4AI serves as a bridge between natural language and Selenium, making it easier to automate UI testing in
a way that is both efficient and intuitive.  

This integration offers substantial benefits for teams looking to streamline their UI validation process.
By enabling a more straightforward way to define and execute Selenium scripts, Tools4AI provides a flexible
framework for automating Selenium-based tests.  

## 📘 JavaDocs

Look at the java docs here - https://javadoc.io/doc/io.github.vishalmysore/tools4ai/latest/index.html
