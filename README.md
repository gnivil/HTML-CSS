# HTML/CSS Challenge - Web Visualization Dashboard (Latitude)

Use HTML and CSS to create a website showcasing weather data analyzed in the SQLAlchemy challenge.
In building this dashboard, we'll create individual pages for each plot and a means by which we can navigate between them. These pages will contain the visualizations and their corresponding explanations. We'll also have a landing page, a page where we can see a comparison of all of the plots, and another page where we can view the data used to build them.

The website must, at the top of every page, have a navigation menu that:
* Has the name of the site on the left of the nav which allows users to return to the landing page from any page
* Contains a dropdown menu on the right of the navbar named "Plots" that provides a link to each individual visualization page
* Provides two more text links on the right: "Comparisons," which links to the comparisons page, and "Data," which links to the data page
* Is responsive (using media queries). The nav must have similar behavior as the screenshots "Navigation Menu" section

-----

## Landing Page
* Contains an  explanation of the project.
* Links to each visualizations page
* Includes a sidebar containing preview images of each plot
* Clicking an image takes users to that visualization

![alt text](https://github.com/gnivil/HTML-CSS/blob/147e49519adad68e6f2c5d4f243ffece758589b1/Images/landingResize.png)

```html
<!DOCTYPE html>
<html lang="en-us">
  <head>

    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">

    <title>Bootstrap Visualization Dashboard</title>

    <!-- Boostrap Stylesheet -->
    <link rel="stylesheet" href="assets/css/bootstrap.min.css" media="screen">

    <!-- Our own CSS stylesheet -->
    <link rel="stylesheet" href="assets/css/styles.css" media="screen">

  </head>

  <body>
    <!-- Start of navbar -->
    <nav class="navbar navbar-default">
      <div class="container-fluid navbar-custom">

        <!-- Brand and toggle get grouped for better mobile display -->
        <div class="row">
          <div class="navbar-header">
            <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1" aria-expanded="false">
              <span class="sr-only">Toggle Navigation</span>
              <span class="icon-bar"></span>
              <span class="icon-bar"></span>
              <span class="icon-bar"></span>
            </button>
            <div class="col-xs-9 phone-nav">
              <a class="navbar-brand" href="#" id="logo">Latitude</a>
            </div>
          </div>

          <!-- Collect the nav links, forms, and other content for toggling -->
          <div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">
            <ul class="nav navbar-nav navbar-right navbar-right-custom">
              <li class="dropdown">
                <a href="#" class="dropdown-toggle" data-toggle="dropdown" role="button" aria-haspopup="true" aria-expanded="false">Plots <span class="caret"></span></a>
                <ul class="dropdown-menu">
                 <li><a href="visualizations/temp.html">Max Temperature</a></li>
                  <li><a href="visualizations/humidity.html">Humidity</a></li>
                  <li><a href="visualizations/cloudiness.html">Cloudiness</a></li>
                  <li><a href="visualizations/wind.html">Wind Speed</a></li>
                </ul>
              </li>
              <li><a href="comparison.html">Comparison</a></li>
              <li><a href="data.html">Data</a></li>
            </ul>
          </div><!-- /.navbar-collapse -->
        </div>
      </div><!-- /.container-fluid -->
    </nav>
    <!-- End of navbar -->

    <!-- Start of container -->
    <div class="container">
      <section class="row">
        <div class="col-md-8">
          <article class="description-content">
            <h1 class="description-header">Summary: Latitude vs. X</h1>
            <hr class="description-hr"/>
            <img src="assets/images/Fig1.png" alt="" id="description-image"/>
            <p>The purpose of this project was to analyze how weather changes as you get closer to the equator. To accomplish this analysis, we first pulled data from the OpenWeatherMap API to assemble a dataset on over 500 cities.</p>
            <p>After assembling the dataset, we used Matplotlib to plot various aspects of the weather vs. latitude. Factors we looked at included: temperature, cloudiness, wind speed, and humidity. This site provides the source data and visualizations created as part of the analysis, as well as explanations and descriptions of any trends and correlations witnessed.</p>
          </article>
        </div>
        <div class="col-md-4">

          <!-- Start of Visualizations imageNav Area -->
          <section id="imageNav-area">
            <div class="imageNav-content">
              <h2 class="imageNav-header">Visualizations</h2>
              <hr />
              <div id="images">
                <a href="visualizations/temp.html"><img src="assets/images/Fig1.png" alt="Latitude vs. Max Temperature" class="imageNav-photo"></a>
                <a href="visualizations/humidity.html"><img src="assets/images/Fig2.png" alt="Latitude vs. Humidity" class="imageNav-photo"></a>
                <a href="visualizations/cloudiness.html"><img src="assets/images/Fig3.png" alt="Latitude vs. Cloudiness" class="imageNav-photo"></a>
                <a href="visualizations/wind.html"><img src="assets/images/Fig4.png" alt="Latitude vs. Wind Speed" class="imageNav-photo"></a>
              </div>
            </div>
          </section>
          <!-- End of the Visualizations imageNav Area -->

        </div>
      </section>
    </div>
    <!-- End of container -->

    <!-- Start of footer -->
    <footer class="footer navbar-fixed-bottom">
      <div class="two-toned-footer-color"></div>
      <p class="text-muted text-muted-footer text-center">
        &copy; Copyright Coding Bootcamp 2017
      </p>
    </footer>
    <!-- End of footer -->

    <!-- jQuery CDN -->
    <script type="text/javascript" src="https://code.jquery.com/jquery-2.1.4.min.js"></script>

    <!-- Bootstrap CDN -->
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js"></script>
  </body>

</html>
```

-----

## Four Visualization Pages
* Descriptive title and heading tag
* Plot/visualization itself for the selected comparison
* A paragraph describing the plot and its significance

-----

## Comparisons Page
* Contains all of the visualizations on the same page to easily compare
* Uses a Bootstrap grid for the visualizations
* The grid must be two visualizations across on screens medium and larger, and 1 across on extra-small and small screens

-----

## Data Page
* Displays a responsive table containing the data used in the visualizations
* The table must be a bootstrap table component
