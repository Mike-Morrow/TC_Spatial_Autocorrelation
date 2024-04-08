<html>
<head>
    <title>TC Advanced Stats Problem 2</title>
    <style>
        body {
            display: flex;
            margin: 0;
            padding: 0;
        }
        #table-of-contents {
            position: fixed;
            left: 0;
            top: 0;
            width: 200px;
            height: 100vh;
            overflow-y: auto;
            padding: 20px;
            background-color: #f0f0f0;
        }
        #content {
            margin-left: 220px;
            padding: 20px;
        }
        iframe {
            max-width: 100%;
        }
    </style>
</head>
<body>

<div id="table-of-contents">
    <h3>Table of Contents</h3>
    <ul>
        <li><a href="#connect-to-data">1 - Connect to data</a></li>
        <li><a href="#build-a-sheet-distribution">2 - Build a sheet to determine the distribution</a></li>
        <li><a href="#build-a-sheet-product-type">3 - Build a sheet by product type</a></li>
        <li><a href="#build-a-sheet-location">4 - Build a sheet by location</a></li>
        <li><a href="#build-a-sheet-day-over-day">5 - Build a sheet day over day</a></li>
        <li><a href="#build-a-sheet-weekday">6 - Build a sheet by weekday</a></li>
        <li><a href="#build-a-sheet-hour-day">7 - Build a sheet by hour of the day</a></li>
        <li><a href="#filter-outliers">8 - Filter out any outliers</a></li>
        <li><a href="#table-extension">9 - Add a table extension</a></li>
        <li><a href="#spatial-autocorrelation">10 - Spatial autocorrelation python code</a></li>
        <li><a href="#join-table-extension">11 - Join the table extension table</a></li>
        <li><a href="#create-sheets">12 - Create sheets for I stat and p value</a></li>
        <li><a href="#pull-into-dashboard">13 - Pull into a dashboard</a></li>
        <li><a href="#data-from-geraldine">14 - Add in data from Geraldine</a></li>
        <li><a href="#average-product-rating">15 - Average product rating by distribution center</a></li>
        <!-- Bonuses -->
        <li><a href="#bonus-calculation">16 - Bonus: Make a calculation for the I stat</a></li>
        <li><a href="#bonus-single-mark">17 - Bonus: Create a sheet with a single mark</a></li>
        <li><a href="#bonus-dynamic-dashboard">18 - Bonus: Create a dynamic dashboard</a></li>
        <li><a href="#bonus-parameterize">19 - Bonus: Parameterize the I stat calculation</a></li>
    </ul>
</div>

<div id="content">
   # TC Advanced Stats Problem 2: Solving the mystery of sporadic reviews with spatial autocorrelation

<h2 id="connect-to-data">1 - Connect to data</h2>

<p>Download the Order Reviews csv file and connect to it in Tableau Desktop.</p>

</br>

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/VU04gc8sYHc?rel=0&si=bIyqfek4s-cm7I4F" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<h2 id="build-a-sheet-distribution">2 - Build a sheet to determine the distribution of product ratings</h2>

<p>Let's begin by exploring our data set to understand what product ratings look like. There are many ways visualization types to represent distribution. Choose one that you see fit.</p>

</br>

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/dTUYIrvXSV0?rel=0&si=i5DzLIH8vuYP4NHz" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<h2 id="build-a-sheet-product-type">3 - Build a sheet to determine the distribution broken down by product type</h2>

<p>Now that you understand the overall distribution, stratify your data by product type and see if you product type affects the average rating?</p>

</br>

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/s_npcT_qavw?rel=0&si=IdAF3TnGwNlKdFmA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<h2 id="build-a-sheet-location">4 - Build a sheet to determine the breakdown of product ratings by location</h2>

<p>How does location impact our product ratings? Experiement with a couple different types of maps.</p>

</br>

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/fR0XB1fY9q8?rel=0&si=9SOni276X7UtdWWb" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<p>As you can see, with rating on color, we can see some discrepancies. We don't know if these are significant, but we will return to this later. </p>

<h2 id="build-a-sheet-day-over-day">5 - Build a sheet to see how product rating trends day over day</h2>

<p>Our data spans 1 month of orders and ratings. Explore how these ratings change day over day.</p>

</br>

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/E1BdFB1OhC8?rel=0&si=sLCFySsPGwPm2hqC" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<h2 id="build-a-sheet-weekday">6 - Build a sheet to answer the question: What is the average product rating by weekday?</h2>

<p>Parse out the weekday (e.g. Sun - Sat) from the order timestamp field and see if you can uncover any insights.</p>

</br>

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/gBeruolL4hw?rel=0&si=Y1gjF4V3gPe9_HKf" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<h2 id="build-a-sheet-hour-day">7 - Build a sheet to answer the question: What is the average product rating by hour of the day? How about by hour of the day and product type?</h2>

<p>Parse out hour of the day from the timestamp and see if there are notable trends. Layer in product type as well.</p>

</br>

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/NADJGnxvX9w?rel=0&si=P9JsYllxU_iYkBIv" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<p>As you can see there are specific hour - product combos that do stick out quite a bit.</p>

<h2 id="filter-outliers">8 - Filter out any outliers in the viz you built in the previous step. We don't want to show any marks that have fewer than 10 underlying records </h2>

<p>Determine how many underlying records are behind each hour - product combo and remove any that are fewer than 10 using a filter. </p>

</br>

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/DNiU-1jLVRU?rel=0&si=DqsOKuo99Dp0GjEK" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<h2 id="table-extension">9 - Add a table extension with Order Reviews.csv as input</h2>

<p>We will now begin configuring our table extension. Begin by dragging out table extension under the existing connection. Then drag out our original data source into the data model as the input of the table extension.</p>

</br>

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/ap6hu9_L5Ok?rel=0&si=kdtruWm_ZoHAF6FS" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<h2 id="spatial-autocorrelation">10 - Copy and paste the spatial autocorrelation python code into the table extension</h2>

<p>Get the autocorrelation code and paste it into the built-in text editor in the data model. Take a few minutes to read through the code to understand the actions it's performing. What do you expect the output to look like? </p>

</br>

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/7zlBiXLjOLI?rel=0&si=JT1aaR2NqEeVbBRB" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<h2 id="join-table-extension">11 - Join the table extension table back into the original data source </h2>

<p>As you saw in the previous step, the table extension does not display an output because we haven't related it back to our original data source. We want to create a relationship between the Order Reviews table and the table extension. Note the table extension only has 2 fields ("I" and "p") and 1 row. How can we build a relationship that ensures we can access these fields in a combined data source? Hint: use a relationship calculation.</p>

</br>

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/SU4JRSb7e1g?rel=0&si=u9GyBejVHmrzbY4i" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<h2 id="create-sheets">12 - Create sheets that display both the I stat and p value </h2>

<p>Create 2 sheets: one for each the I statistic and another for the corresponding p value. </p>

</br>

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/NK2SBlOaBPw?rel=0&si=1wcXFV5ahMj3C3xu" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<h2 id="pull-into-dashboard">13 - Pull the I stat and p value sheets into a dashboard along with a map of all order locations colored by product rating</h2>

<p>Let's combine those 2 sheets from the previous step into a dashboard along with a map of all locations colored by rating.</p>

</br>

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/ktdUaX_k464?rel=0&si=pCk74kyERO9avK27" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Given the patterns we've found in the product ratings across location, we reach out to Geraldine in logistics who is able to send us data on distribution centers!

<h2 id="data-from-geraldine">14 - Add in the data received from Geraldine, create a relationship based on Order ID</h2>

<p>Go back to the data pane and update your model to include Geraldine's data on distribution centers. </p>

</br>

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/dYRHw_n5xoQ?rel=0&si=WcINYI-cBp9Va5ZO" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<h2 id="average-product-rating">15 - Build a sheet that answers the question: what is the average product rating by distribution center?</h2>

<p>Does distribution center look like a significant variable?</p>

</br>

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/yMWEAl47K-Y?rel=0&si=xF7UwUx-l17jXH9F" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<p>Similar to the Broad Street Pump example from the 1854 Cholera outbreak, we clearly see location as a significant factor with the underlying distribution centers as the root cause. It's time to call up Geraldine's boss to see what's happening inside San Diego and Redding distribution centers!</p>


<h2 id="bonus-calculation">16 - Bonus: Make a calculation for the I stat using TabPy in a calculated field</h2>

<p>Before table extensions, TabPy was used inside a calculated field that acted as a table calculation. Create a "Script_Real" calculation that computes the I statistic.</p>

</br>

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/6B6PsdHExvY?rel=0&si=PTeXAFkc6OOw4Lml" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<h2 id="bonus-single-mark">17 - Bonus: Create a sheet with a single mark that shows the I stat </h2>

<p>Make sure we can see the I statistic on a single sheet as a single mark. Check to confirm the value is the same as what you got with the table extension. </p>

</br>

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/reJ3a3gjfBU?rel=0&si=Te5EomMXy4bhz_PA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<h2 id="bonus-dynamic-dashboard">18 - Bonus: Create a dynamic dashboard that shows the map of all locations, the I stat, and the ability to filter by Product Type </h2>

<p>With the sheet you created, add it to a dashboard with a map of locations. Add in a filter for product type and test out the interactivity.</p>

</br>

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/QxKHY3O7Tc0?rel=0&si=g656MxBvA5vkzAjO" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<h2 id="bonus-parameterize">19 - Bonus: Parameterize the I Stat calculation so that it can be computed for both Product Rating and Product Price. Update the dashboard with this new functionality</h2>

<p>Can you update the I stat calculation to let the end user toggle between Product Rating and Product Price to recompute the I stat? If so, add that option to the dashboard and explore new insights. What did you find?</p>

</br>

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/I0Y2mcrhr3U?rel=0&si=yU1NJSX4hUhciw97" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<p>Congrats on making it to the end! </p>

</div>

<script>
    // Optional: Implement any JavaScript here for additional functionality (such as smooth scrolling)
</script>

</body>
</html>
