# IPL-score-and-winner-prediction
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title>First Innings Score Predictor</title>

        <!-- Favicon -->
        <link rel="shortcut icon" href="{{ url_for('static', filename='ipl-favicon.ico') }}">
        <!-- External CSS File -->
        <link rel="stylesheet" type="text/css" href="{{ url_for('static', filename='styles.css') }}">
        <!-- Font Awesome CDN -->
        <script src="https://kit.fontawesome.com/5f3f547070.js" crossorigin="anonymous"></script>
        <!-- Google Fonts -->
        <link href="https://fonts.googleapis.com/css2?family=Open+Sans:wght@300&display=swap" rel="stylesheet">
    </head>

    <body>

        <!-- Website Title -->
    	<div class="container">
            <h2 class='container-heading'><span class='heading_first'>First Innings Score Predictor for </span><span class="heading_second">Indian Premier League (IPL)</span></h2>
            <div class='description'>
    			<p>A Machine Learning Web App, Built with Flask, Deployed using Heroku.</p>
    		</div>
    	</div>

        <!-- Prediction Area -->
        <div class="prediction-area">

            <!-- IPL Banner - 1 -->
            <div class='ipl-banner-left'>

                <div class="slider-frame">
                    <div class="slide-images-up">

                        <!-- Image-1 -->
                        <div class="image-container">
                            <img class="image-width" src="{{ url_for('static', filename='mi.jpg') }}" alt="Mumbai Indians">
                        </div>
                        <!-- Image-2 -->
                        <div class="image-container">
                            <img class="image-width" src="{{ url_for('static', filename='srh.png') }}" alt="Sunrisers Hyderabad">
                        </div>
                        <!-- Image-3 -->
                        <div class="image-container">
                            <img class="image-width" src="{{ url_for('static', filename='rcb.png') }}" alt="Royal Challengers Bangalore">
                        </div>
                        <!-- Image-4 -->
                        <div class="image-container">
                            <img class="image-width" src="{{ url_for('static', filename='dc.png') }}" alt="Delhi Capitals">
                        </div>
                        <!-- Image-5 -->
                        <div class="image-container">
                            <img class="image-width" src="{{ url_for('static', filename='rr.png') }}" alt="Rajasthan Royals">
                        </div>
                        <!-- Image-6 -->
                        <div class="image-container">
                            <img class="image-width" src="{{ url_for('static', filename='kkr.jpg') }}" alt="Kolkata Knight Riders">
                        </div>
                        <!-- Image-7 -->
                        <div class="image-container">
                            <img class="image-width" src="{{ url_for('static', filename='kxip.png') }}" alt="Kings XI Punjab">
                        </div>
                        <!-- Image-8 -->
                        <div class="image-container">
                            <img class="image-width" src="{{ url_for('static', filename='csk.png') }}" alt="Chennai Super Kings">
                        </div>

                    </div>
                </div>

            </div>

            <!-- Prediction Form -->
            <div class='div2'>
                <form action="{{ url_for('predict') }}" method="POST">
                    <!-- Batting Team Dropdown -->
                    <select class="form-input align-center" name="batting-team">
                        <option value="none">--- Select a Batting team ---</option>
                        <option value="Mumbai Indians">Mumbai Indians</option>
                        <option value="Kolkata Knight Riders">Kolkata Knight Riders</option>
                        <option value="Chennai Super Kings">Chennai Super Kings</option>
                        <option value="Rajasthan Royals">Rajasthan Royals</option>
                        <option value="Kings XI Punjab">Kings XI Punjab</option>
                        <option value="Royal Challengers Bangalore">Royal Challengers Bangalore</option>
                        <option value="Delhi Daredevils">Delhi Daredevils</option>
                        <option value="Sunrisers Hyderabad">Sunrisers Hyderabad</option>
                    </select><br>
                    <!-- Bowling Team Dropdown -->
                    <select class="form-input align-center" name="bowling-team">
                        <option value="none">--- Select a Bowling team ---</option>
                        <option value="Mumbai Indians">Mumbai Indians</option>
                        <option value="Kolkata Knight Riders">Kolkata Knight Riders</option>
                        <option value="Chennai Super Kings">Chennai Super Kings</option>
                        <option value="Rajasthan Royals">Rajasthan Royals</option>
                        <option value="Kings XI Punjab">Kings XI Punjab</option>
                        <option value="Royal Challengers Bangalore">Royal Challengers Bangalore</option>
                        <option value="Delhi Daredevils">Delhi Daredevils</option>
                        <option value="Sunrisers Hyderabad">Sunrisers Hyderabad</option>
                    </select><br>
                    <input class="form-input" type="text" name="overs" placeholder="Overs (>= 5.0) eg. 7.2"><br>
                    <input class="form-input" type="text" name="runs" placeholder="Runs eg. 64"><br>
                    <input class="form-input" type="text" name="wickets" placeholder="Wickets eg. 4"><br>
                    <input class="form-input" type="text" name="runs_in_prev_5" placeholder="Runs scored in previous 5 Overs eg. 42"><br>
                    <input class="form-input" type="text" name="wickets_in_prev_5" placeholder="Wickets taken in previous 5 Overs eg. 3"><br>

			<input type="submit" class="myButton" value="Predict Score">
        	</form>
            </div>

            <!-- IPL Banner - 2 -->
            <div class='ipl-banner-right'>

                <div class="slider-frame">
                    <div class="slide-images-down">

                        <!-- Image-1 -->
                        <div class="image-container">
                            <img class="image-width" src="{{ url_for('static', filename='mi.jpg') }}" alt="Mumbai Indians">
                        </div>
                        <!-- Image-2 -->
                        <div class="image-container">
                            <img class="image-width" src="{{ url_for('static', filename='srh.png') }}" alt="Sunrisers Hyderabad">
                        </div>
                        <!-- Image-3 -->
                        <div class="image-container">
                            <img class="image-width" src="{{ url_for('static', filename='rcb.png') }}" alt="Royal Challengers Bangalore">
                        </div>
                        <!-- Image-4 -->
                        <div class="image-container">
                            <img class="image-width" src="{{ url_for('static', filename='dc.png') }}" alt="Delhi Capitals">
                        </div>
                        <!-- Image-5 -->
                        <div class="image-container">
                            <img class="image-width" src="{{ url_for('static', filename='kkr.jpg') }}" alt="Kolkata Knight Riders">
                        </div>
                        <!-- Image-6 -->
                        <div class="image-container">
                            <img class="image-width" src="{{ url_for('static', filename='rr.png') }}" alt="Rajasthan Royals">
                        </div>
                        <!-- Image-7 -->
                        <div class="image-container">
                            <img class="image-width" src="{{ url_for('static', filename='kxip.png') }}" alt="Kings XI Punjab">
                        </div>
                        <!-- Image-8 -->
                        <div class="image-container">
                            <img class="image-width" src="{{ url_for('static', filename='csk.png') }}" alt="Chennai Super Kings">
                        </div>

                    </div>
                </div>

            </div>
        </div>

        <!-- Footer -->
       <div class='footer'>
           <div class="contact">
               <a target="_blank" href=""><i class="fab fa-github fa-lg contact-icon"></i></a>
           </div>
       </div>

    </body>
</html>
