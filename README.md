# Coding Dojo Bootcamp Assignment  
## Web Fundamentals / API and AJAX / Your Very Own Weather Forecast App!

### Submit Files
```
yourVeryOwnWeatherForecastApp.html
yourVeryOwnWeatherForecastApp.css
yourVeryOwnWeatherForecastApp.js
```

### Assignment details  
Let's build a weather forecast application where we can input any city and find out the temperature in Fahrenheit. Thankfully there is an API or a set of URLs out there that will tell us the temperature of any city! We will be using the Open Weather API. Open Weather API gives us a set of very useful URLs that are fun to use. For example, navigate to the link   http://api.openweathermap.org/data/2.5/weather?q=London,uk&&appid= (make sure you add your API)... and you will find JSON data about London. In fact, even if you try to navigate to http://api.openweathermap.org/data/2.5/weather?q=California,us&&appid=(with your API id)..., the API will find you the same JSON data. This means that we have to validate different users' responses less on our application. Thanks, Open Weather API!

We are going to have a form where our user can enter a city in a form and have the city's temperature displayed on the screen. We will be listening for a form to be submitted so that we can gather what the user has filled out and add it to our URL http://api.openweathermap.org/data/2.5/weather?q=. For example, if the user has typed in 'Los Angeles', we would add this input to http://api.openweathermap.org/data/2.5/weather?q= so that the URL ends up being http://api.openweathermap.org/data/2.5/weather?q=Los Angeles. And do not forget to add the API key at the last part of the URL!

We can listen to a form being submitted with jQuery's submit() function. However, the submit() function automatically reloads the page so we are going to be returning false. Now that we know how to do AJAX we don't want our page to reload: we want the data to come to us and then we can dynamically update the parts that need to be updated in our current page. This should be a good starting point for setting up your jQuery to build this application.

```
$(document).ready(function() {
    $('form').submit(function() {
        // your code here (build up your url)
        $.get(url, function(res) {
            // your code here
        }, 'json');
        // don't forget to return false so the page doesn't refresh
        return false;
    });
});
```

