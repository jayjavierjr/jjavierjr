# Planit Technical Assessment – Performance Test Challenge
+ **Applicant Name**: Jay B. Javier Jr
+ **Assessment Given**: 11-Aug-2022
+ **Assessment Completed**: 12-Aug-2022
+ **Tool Used**: Apache JMeter
+ **Web Application**: https://duckduckgo.com/

<br />

## Requirements
### **Prerequisites**:
- Installed Java for Windows
- Working Apache JMeter for Windows
  - Basic understanding on JMeter navigation
- Stable internet connection

### **Test Steps**

  |Step No. |Transaction Name                     |Step Description                                 |Test Data                |
  |---      |---                                  |---                                              |---                      |
  |1        |01_LoadDuckDuckGoHomePage            |Open browser and access the duckduckgo website   |https://duckduckgo.com/  |
  |2        |02_TypeSuggestedSearchTerm           |Type the Search Term value in the search box     |Search Terms: Planit, Performance, Testing, Cloud, Training |
  |3        |03_SelectSearchTermFromSuggestionBox |Select Search Term from the suggested Search Box |                         |

- Each search term should be searched for three times
- Scripts should be in a complete and runnable state

<br />

## **Test Artifacts**
This repositories contains the following files:
<br />
![image](https://user-images.githubusercontent.com/86303472/184123952-0fce34b3-b53d-4b50-9f17-62bffeeb0993.png)
<br />
- **jayjavierjr** - main folder which contains all test artifacts
  - **CSVTestData** - contains the CSV file which holds the test data used in the JMeter performance test script
  - **PerformanceTestScript** - contains the developed JMeter performance test script

<br />

## **Technical Notes**
- **Regular Expression** was used to extract the dynamic values
- **JSR223 PostProcessor** was used to fetch the length of the search string
  ```
  vars.put('nWordLen', vars.get('SearchTerms').length() as String);
  ```
  <img src="https://user-images.githubusercontent.com/86303472/184127710-0c1b44e1-b4e9-4fb3-a22e-ef702d8c578b.png" width="750px">
- **JSR223 PreProcessor**, **Loop Controller** & a **Counter** was used to loop through each of the letters in the search string
  ```
  vars.put('searchWord', vars.get('SearchTerms').substring(0,vars.get('Count') as int));
  ```
  <img src="https://user-images.githubusercontent.com/86303472/184127898-13f8575d-5943-4122-8b64-cce6c87bc053.png" width="750px">
- **Think Time** was set to 5 seconds per transactions
- **CSV Data Set Config Element** was configured to use relative path on the test data file.
- **Thread Group - Loop Count** was set to 15 to make sure that search string will be search for 3 times

<br />

## **How To Run**
1. Open the ‘**JMeter**’ > Click ‘**Open**’ icon > Browse to your cloned path > Open ‘**PlanitPerformanceTestAssessment_JayJavierJr.jmx**’ <img src="https://user-images.githubusercontent.com/86303472/184125298-2bcf9aa9-768a-4fa2-b01a-f1397f7dfbb5.png" width="750px">
2. Once opened > Click on ‘**Run**’ button > Click on ‘**View Results Tree**’  <img src="https://user-images.githubusercontent.com/86303472/184125880-19dcdfba-e531-4bd6-a461-16ba1432c50b.png" width="750px">

### **IMPORTANT: Script was tested working with no errors as of this writing.**



<!--
**jayjavierjr/jayjavierjr** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
