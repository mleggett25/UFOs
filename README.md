# UFO Analysis with Javascript and HTML

## Overview of Analysis

### Purpose
The purpose of this project was to create a website that would provide an in-depth analysis of UFO sightings by allowing users to filter for multiple criteria at the same time.

## Results: How to Perform a Search
To allow the user to search through the UFO data, I created a container in the HTML file that would allow the user to filter the data based on five criteria: Date, City, State, Country, and Shape.

```
<div class="container-fluid">
  <div class="row">
    <div class="col-md-3">
      <form>
          <p>Filter Search</p>
      </form>
      <ul class="list-group">
          <li class="list-group-item bg-dark">
              <label for="datetime">Enter Date</label>
              <input type="text" id="datetime" placeholder="1/10/2010">
          </li>
          <li class="list-group-item bg-dark">
              <label for="city">Enter City</label>
              <input type="text" id="city" placeholder="fresno">
          </li>
          <li class="list-group-item bg-dark">
            <label for="state">Enter State</label>
            <input type="text" id="state" placeholder="ca">
          </li>
          <li class="list-group-item bg-dark">
            <label for="country">Enter Country</label>
            <input type="text" id="country" placeholder="us">
          </li>
          <li class="list-group-item bg-dark">
            <label for="shape">Enter Shape</label>
            <input type="text" id="shape" placeholder="circle">
          </li>
      </ul>
    </div>
 ```

This script creates the Filter Search area on the webpage.

![Filter Search Box](static/images/filters.PNG)

In order for the user-inputted search criteria to work on the UFO data, I had to create a function that saves the element, value, and ID of the filter that was changed.

```
var filters = {};

function updateFilters() {

    let changedElement = d3.select(this);
    
    let elementValue = changedElement.property("value");
    console.log(elementValue)

    let filterId = changedElement.attr("id");
    console.log(filterId)

    if (elementValue) {
      filters[filterId] = elementValue;
    }
    else {
      delete filters[filterId];
    }
  
    filterTable();
  }
```

I then created a function that loops through the UFO data and keeps only the results that match the user-inputted search criteria.

```
  function filterTable() {
  
    let filteredData = tableData;
  
    for (fil in filters) {
      filteredData = filteredData.filter(row => row[fil] === filters[fil]);
     };

    buildTable(filteredData);
    }

  d3.selectAll("input").on("change", updateFilters);
  
  buildTable(tableData);
```

This script now allows for the user to search through the UFO data by using the filter options. Here is the webpage as it exists without any filters:

![UFO Webpage No Filters](static/images/webpage_no_filters.PNG)

If the user were to input search criteria into the filters such as 1/1/2010 into Date, ca into State, and triangle into Shape, the webpage would filter the UFO data and produce only data that matches the criteria:

![UFO Webpage Filters](static/images/webpage_filters.PNG)
