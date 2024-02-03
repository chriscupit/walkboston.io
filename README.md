# walkboston.io
Walk Boston Data Project

1. Walk through Boston public salaries data
When building web applications, you will often find yourself working with dynamic data that you can manipulate and display on a web page. This data is usually provided by a web server or a database. Data comes to you via a web server in a specific format called JSON.
According to JSON.org:
JSON (JavaScript Object Notation) is a lightweight data-interchange format. It is easy for humans to read and write. And, it is easy for machines to parse and generate.
In this activity, you’re going to loop through a set of JSON data which has been converted to an array representing Boston employee salaries to find the top five income earners in the city of Boston. The data has already been converted to an array, and as you can see, due to the size of the file, you cannot view it without downloading it. You are free to do so if you’d like to look at the data, but as its already an array, you do not need to take any additional steps to clean up the data.
The starter code you’re given displays the list of employees and their salaries. It includes:
data.js: This file contains Boston employees’ salary data. This data is in the JSON format, and has already been converted to an array, so that you can work with array methods in your program. You do not need to do anything further to edit the data! Here’s an example of the data for a single employee:
"data":[
   [
      1,
      "17439B12-1A55-4B6A-980E-5BAC15841AC4",
      1,
      1426008064,
      "525314",
      1426008064,
      "525314",
      "{\n}",
      "Adario,Anthony J", // employee name
      "Supvising Claims Agent (Asd)",
      "ASD Human Resources",
      "98538.32", //employee salary
      "0.00",
      "1842.87",
      "0.00",
      "0.00",
      "0.00",
      "0.00",
      "100381.19",
      "02132"
   ]
]
As you can see, the name of the employee is commented on line 8, and their salary is commented on line 11. This will be useful to you when you are comparing employee’s salaries to each other as well as finding the top five earners later on. Keep in mind, the data has been formatted for you into an array, so you can use array methods on it, like splice, slice, sort, and filter.
index.html: This in the HTML file used to display data in your NextTech browser. DO NOT edit this file.
Instead of editing your index.html file, when you are ready to display the data, do so by dynamically creating HTML elements and injecting the data into them, as Professor Williams did during his initial demonstration. You will do this in the walkboston.js file described below. Here is an example where all the posts are rendered:
function renderPosts(boston, container) {
  var people = boston.data;
  const len = boston.data.length;
  var html = "";
  for (let i = 0; i < len; i++) {
    html +=
      '<li class="post">' +
      "<h2>" +
      people[i][8] +
      "</h2>" +
      "<h3>" +
      people[i][11] +
      "</h3>";
  }
  container.innerHTML = '<ul id = "data">' + html + "</ul>";
}
walkboston.js: This is the JavaScript file where you will write the function which finds the top five earners in the city of Boston, and render then on the webpage.
Your task is to write JavaScript code that will display the top five earners in Boston (salaries) on the web page
Note:
The HTML element containing the top earners should have an ID of “topSalaries”
The name data of the employee is at index 8 in the array, and the salary data is at index 11
You should display the name of the employee and the total salary earned by them
You will have to use comparison operators to check and see if each person in the array of employees earns more or less than the previous person in the array. To find out more information, check out array.sort().
You will need to filter out any people who make more than 200k annually to complete the second section of the exercise. Check out array.filter() to learn more and get some ideas for how to do this.
