# UFO Analysis with Javascript and HTML

## Overview of Analysis

### Purpose
The purpose of this project was to create a website that would provide an in-depth analysis of UFO sightings by allowing users to filter for multiple criteria at the same time.

## Results: How to Perform a Search
To allow the user to search through the UFO data, I created a container that would allow the user to filter the data based on five criteria: Date, City, State, Country, and Shape.

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
