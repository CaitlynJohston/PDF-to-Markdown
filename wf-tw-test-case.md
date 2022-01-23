##### Submitted by Caitlyn Johnston .  22 Jan 2022

Assumptions: 
1. The table formatting would be determined by CSS that's not part of this file.
2. The colors in the code snippet in the PDF are not needed in the markdown code block.


—————
<font color="a569bd">Suggestion: Add a table at the beginning called Terms defining the acronyms and abbreviations used in the document because not everyone, especially new users and new hires, will be familiar with them. My best guesses are below but there could very well be industry- or company-specific ones with the same letters.
Example:
### **Terms and Definitions**

|  <b>Term       |       Definition</b>  | 
| :---: |  --- |
| BP | Bot protocol? Business process? | 
| CSV | A text-based spreadsheet format  | 
| HTTP | Hypertext transfer protocol | 
| IDE | integrated development environment |
| URL | Universal resource locator | 
| XML | Extensible Markup Language. A machine language similar to HTML. | 
---
Also, have a company-wide glossary page that's all-inclusive with acronyms and terms for all departments.</font>

**Bot Tasks** contain work to be done by WorkFusion’s Bot. These Bots perform the steps in your Business Process which are more suited for automation than human labor. Bot Tasks exist only as Business Process steps. <font color="a569bd"> NOTE: I'd double check this with someone to make sure it's right.</font>

For example: Address parsing to determine the width and height of an image, interaction with your API or repository, or filtering out content that does not meet certain criteria.

**Bot Configs** are written using the Web-Harvest library and are executed for each record separately. For writing Web-Harvest XML configs, use pre-defined Web-Harvest XML elements described here or WorkFusion plugins.

**Bot Config Bundle** is a bundled Java library containing a bot config and a Java code reference that can be used in this bot config.

# How to Create, Test, and Run Bot Tasks
<ol>
<li> Create and test a Web-Harvest config using the WorkFusion Studio (Eclipse-based IDE).
<li> Create a Bot Use Case in WorkFusion. 
<li> Choose the Bot Use Case type. Note: ETL is the best practice because it fits better for reusing and adds flexibility. <font color="a569bd">NOTE: I'd check this to make sure I understand it and ensure this is the best phrasing.</font>
<li> Create a BP and include a Bot Step based on this Use Case. Alternatively, use the WorkFusion Repository and import a Bot Config Bundle.
<li> Test the Bot Config in BP using a small input batch.

-  Optional: Make changes, if needed, to column names, use proxy, datastore connection, and output-column names, etc.

<li> Update the Bot Use Case and use it in your production BP.
</ol>
Alternatively, create a Bot Task from scratch in BP under the Design Process tab. Use a blank Use Case and paste your code in, but this approach leads to multiple issues. <font color="a569bd"> NOTE: I'd check this to make sure I understand it and rewrite it with the best practice recommendation.</font>

# Execution Details

Submission configurations require XML and each record is executed once. For example, if the input CSV file contains 40 Records, the Web-Harvest XML configuration will be executed 40 times.

If an error occurs, the Bot Config will run five times.

# Results

The results of a Bot Task are defined in the `<export>` plugin settings.

All the columns created by the Bot Task can be used in further BP steps for both Manual and Bot.

# Hello World Example

The following example:

1. <font color="a569bd">Missing a noun here. The system? I'd check with a SME.</font> gets HTTP response from URLs listed in the `url_to_check` column of the input data file.
2. <font color="a569bd">The system</font> records the HTTP response into the `http_response` variable.
3. <font color="a569bd">The system</font> exports all original columns and appends a new `http` column containing the `http_response` variable value.

Bot Config Example

     <?xml version="1.0" encoding="UTF-8"?>
     <config>
     <!--defining variable-->
     <var-def name="http_response">
     <!--passing the appropriate value from url_to_check column in input data file as a parameter for http plugin-->
     <http url="${url_to_check}"></http> </var-def>

     <!--exporting all original input columns-->
     <export include-original-data="true">
     <!--adding a new column with the http plugin result to the export file-->
     <single-column name="http" value="${http_response}"/> </export>
     </config>


