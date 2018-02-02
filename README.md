## Website Performance Optimization portfolio project
------------------------------------------------------------

### Summary
------------------------------------------------------------
The purpose of this project is to optimize the website by optimizing the critical rendering path through methods learned 
in the Udacity Web Optimization course and Critical rendering Path score.

### Running Instructions
-------------------------------------------------------------
1. Clone the repo locally.
2. Navigate to pizza.html to run the app locally.
3. In DevTools, under the Performance tab, record a timline while scrolling to check the framerate.
4. In Google PageSpeed, you may check the optimization score. 
5. For testing the app in a mobile device see instructions below.

#### Phone Inspection Steps
-------------------------------------------------------------
To inspect the site on your phone: 
* You can run a local server by doing: 

  ```bash
  $> cd /path/to/your-project-folder
  $> python -m SimpleHTTPServer 8080
  ```

* Open a browser and visit localhost:8080
* Download and install [ngrok](https://ngrok.com/) to the top-level of your project directory to make your local server accessible remotely.

  ``` bash
  $> cd /path/to/your-project-folder
  $> ./ngrok http 8080
  ```

* Copy the public URL ngrok gives you and try running it through PageSpeed Insights! 


### Results
---------------------------------------------------------------
##### Before
Initially, the time to resize pizzas was just over 100ms which can be vastly improved.
In addition, I used the DevTools timeline feature to see what was going on when i scrolled up and down. As you can see in the picture, there is a Layout error. The warning states: "___Forced reflow___ is likely a performance bottleneck".

##### After
The time to re-size pizzas dropped to around 1ms.
The timeline in DevTools shows that there are no more Layout errors.


### Optimizations in pizza.html
---------------------------------------------------------------
* In the changePizzaSizes function:
	* Assigned the querySelector to the variable "randomPizza" and moved it outside the for loop so it does not generate with every pass.
	* Also, moved the dx and newWidth declarations outside the for loop.
* Moved 'pizzasDiv outside of the for loop so it only gets generated once when the page loads.	
* Saved the querySelector for 'movingPizzas1' to the 'movingPizzas' variable and moved it outside the for loop so it only generates once.
* Set the number of the pizzas on Display to be dependent on the height of the screen.


#### Optimization Tips and Tricks
---------------------------------------------------------------
* [Optimizing Performance](https://developers.google.com/web/fundamentals/performance/ "web performance")
* [Analyzing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/analyzing-crp.html "analyzing crp")
* [Optimizing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/optimizing-critical-rendering-path.html "optimize the crp!")
* [Avoiding Rendering Blocking CSS](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-blocking-css.html "render blocking css")
* [Optimizing JavaScript](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/adding-interactivity-with-javascript.html "javascript")
* [Measuring with Navigation Timing](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/measure-crp.html "nav timing api"). We didn't cover the Navigation Timing API in the first two lessons but it's an incredibly useful tool for automated page profiling. I highly recommend reading.
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/eliminate-downloads.html">The fewer the downloads, the better</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer.html">Reduce the size of text</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization.html">Optimize images</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/http-caching.html">HTTP caching</a>

### Customization with Bootstrap
The portfolio was built on Twitter's <a href="http://getbootstrap.com/">Bootstrap</a> framework. All custom styles are in `dist/css/portfolio.css` in the portfolio repo.

* <a href="http://getbootstrap.com/css/">Bootstrap's CSS Classes</a>
* <a href="http://getbootstrap.com/components/">Bootstrap's Components</a>

#### Resources used:
---------------------------------------------------------------
* Udacity FSL quiz (8.10) [Stop FSL Link](https://classroom.udacity.com/nanodegrees/nd001/parts/e87c34bf-a9c0-415f-b007-c2c2d7eead73/modules/273584856175461/lessons/4147498575/concepts/41542085800923)
* Udacity forums on Web Optimization Project. 
* Dillinger.io for ReadMe formatting. 

