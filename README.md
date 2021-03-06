<meta charset="UTF-8">
<link rel="stylesheet" type="text/css" href="style.css">
	
<script src="script.js"></script>
		
<html lang="en-us">

<head>
 <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
    <title>YouTube API Home</title>
    <meta name="heywords" content="" />
    <meta name="description" content="content1"/>
    <meta name="viewport" content="width=device-width, initial-scale=20">
    <meta name="theme-color" content="#157878">
    <link href="http://fonts.googleapis.com/css?family=Varela" rel="stylesheet" />
    <link href="default.css" rel="stylesheet" type="text/css" media="all" />
    <link href="fonts.css" rel="stylesheet" type="text/css" media="all" />
    
<html>
<head>
<style>
body {
    margin: 0;
    font-family: 'Lato', sans-serif;
}

.overlay {
    height: 100%;
    width: 0;
    position: fixed;
    z-index: 1;
    top: 0;
    left: 0;
    background-color: rgb(0,0,0);
    background-color: rgba(0,0,0, 0.9);
    overflow-x: hidden;
    transition: 0.5s;
}

.overlay-content {
    position: relative;
    top: 25%;
    width: 100%;
    text-align: center;
    margin-top: 30px;
}

.overlay a {
    padding: 8px;
    text-decoration: none;
    font-size: 36px;
    color: #818181;
    display: block;
    transition: 0.3s;
}

.overlay a:hover, .overlay a:focus {
    color: #f1f1f1;
}

.overlay .closebtn {
    position: absolute;
    top: 20px;
    right: 45px;
    font-size: 60px;
}

@media screen and (max-height: 450px) {
  .overlay a {font-size: 20px}
  .overlay .closebtn {
    font-size: 40px;
    top: 15px;
    right: 35px;
  }
}
</style>
</head>
<body>

<div id="myNav" class="overlay">
  <a href="javascript:void(0)" class="closebtn" onclick="closeNav()">&times;</a>
  <div class="overlay-content">
    <a onclick="closeNav()" href="#aboutThisGuide">Introduction</a>
    <a onclick="closeNav()" href="#embedVideo">How to interact with it</a>
    <a onclick="closeNav()" href="#queueFunctions">Queuing Functions</a>
    <a onclick="closeNav()" href="#eventsPage">Event Handlers</a>
    <a onclick="closeNav()" href="#playbackControls">Playback Controls</a>
    <a onclick="closeNav()" href="#exampleVideo">Example Video</a>
  </div>
</div>


<span style="font-size:30px;cursor:pointer" onclick="openNav()">&#9776; Menu</span>

<script>
function openNav() {
    document.getElementById("myNav").style.width = "100%";
}

function closeNav() {
    document.getElementById("myNav").style.width = "0%";
}
</script>
     
</body>
</html>


  </head>
  <body>

   <!-- <section class="main-content">
      <h2 id="youtube-iframe-api">YouTube iFrame API</h2>
 
<!--<nav class="navigation">
			<p> <b>Navigation</b> </p>
			<ul class="menu">	
				<li><a href="#top">Title</a></li>
				<li><a href="#aboutThisGuide">About the Guide</a></li>
				<li><a href="#embedVideo">Embedding a Video</a></li>
				<li><a href="#queueFunctions">Queuing Functions</a></li>
				<li><a href="#eventsPage">Event Handlers</a></li>
				<li><a href="#playbackControls">Playback Controls</a></li>
				<li><a href="#exampleVideo">Example Video</a></li>
			</ul>
		</nav> -->

	<div class="outer">
	<div class="inner-title">
	<center><h1>The Basics of YouTube API</h1>
	<h4><font>By: Melissa Barr </font></h4></center>
	<br />
	</div>
	</div>
	
	<html>
  <body>
    <!-- 1. The <iframe> (and video player) will replace this <div> tag. -->
    <div id="player"></div>

    <script>
      // 2. This code loads the IFrame Player API code asynchronously.
      var tag = document.createElement('script');

  tag.src = "https://www.youtube.com/iframe_api";
     var firstScriptTag = document.getElementsByTagName('script')[0];
     firstScriptTag.parentNode.insertBefore(tag, firstScriptTag);

      // 3. This function creates an <iframe> (and YouTube player)
      //    after the API code downloads.
      var player;
      function onYouTubeIframeAPIReady() {
        player = new YT.Player('player', {
          height: '430',
          width: '700',
          videoId: '0HTexqxo1og',
          events: {
            'onReady': onPlayerReady,
            'onStateChange': onPlayerStateChange
          }
        });
      }

      // 4. The API will call this function when the video player is ready.
      function onPlayerReady(event) {
        event.target.playVideo();
      }

      // 5. The API calls this function when the player's state changes.
      //    The function indicates that when playing a video (state=1),
      //    the player should play for six seconds and then stop.
      var done = false;
      function onPlayerStateChange(event) {
        if (event.data == YT.PlayerState.PLAYING && !done) {
          setTimeout(stopVideo, 900000);
          done = true;
        }
      }
      function stopVideo() {
        player.stopVideo();
      }
    </script>
  </body>
</html>	
	<div class="outer">
	<div id="aboutThisGuide"></div>
			<div class="inner-heading">	
				<h2>Introduction</h2>
			</div>
			<div class="inner-body">
					
		<h5>What is the YouTube IFrame API?</h5>
		<p><left>The Iframe player API is a program that lets you embed a YouTube video player into your website and lets you program it to your specifications using JavaScript. There are many ways to personalize it. </left></p>
		<table class="offset">
				<tr>
					<th>For example you can:</th>
				</tr>
					<td>1. Play</td>
				<tr>
					<td>2. Pause</td>
				</tr>
					<td>3. Stop</td>
				<tr>
					<td>4. Adjust player volume</td>
				</tr>
					<td>5. Retrieve information about the video</td>
				<tr>
					<td>6. Add event listeners</td>
				</tr>
		</table>
				
		<p><left>I choose to do this program because it is a useful tool that can be added to any website either to support information, explain ideas, or just for fun!</left></p>
		<p><left>Here is where you can find the software and existing documentation for the YouTube IFrame API. Credit is given for code experts. 
		<a href="https://developers.google.com/youtube/iframe_api_reference">https://developers.google.com/youtube/iframe_api_reference</a></left></p>	
		<br /><div class="blackBar"></div><br />		
			<h2>Getting Started: How do you set it up?</h2>
			<h4>Requirements</h4>
			<p><left>There are a few requirements that you need:
					<li>A browser that supports the HTML5 postMessage feature (most browsers do but keep in mind that Internet Explorer 7 does not support this)</li>
					<li>The player must have an area at least 200px by 200px to play the video and if you decide to include controls then it must have room for that as well</li>
					<li>Must use the <code>onYouTubeIframeAPIReady</code> function - we will explain more on this later</li>
					<br /><br />Here is a sample HTML code that creates an embedded player that will load a video. Code explained below.</left></p>
					
	<img src="HTMLexampleYouTubeAPI.png" alt="YouTubeAPI" style="width:650px;height:800px;">
	
	<p><left>So lets talk about what’s going on here. 
	<br/><br/>Starting at the top at #1, the <code>&lt;div&gt;</code> tag is used to get the location on the page of where the video player will be placed. This is identified by the id to make sure that the <code>&lt;iframe&gt;</code> places it in the correct location.
	<br/><br/>Continuing on to #2, this is the part of the code that actually loads the Iframe Player API JavaScript code. The <code>&lt;script&gt;</code> part is needed to asynchronously download the code. It is important to keep in mind that this is not yet supported in all modern browsers.
	<br/><br/>Remember when we mentioned the <code>onYouTubeAPIReady</code> function before? This is where it comes into play. It is used to execute the code as soon as the player downloads. What is is actually doing is contracting a video player object but to phrase that in easier to understand terms it is defining the terms of the player and getting ready to play the video. There are a few ways to personalize this which we will go into detail in a bit but as shown you can specify the height, width, and when it plays.
	<br/><br/>While the previous function gets the video ready to play, the <code>onPlayerReady</code> function plays the video when it is ready. Again, this depends on the settings you have programmed it to.
	<br/><br/>Lastly #5 is all about changing the state of the player. The <code>onPlayerStateChange</code> function is for when the state of the player changes. This includes any of the 6 ways to personalize the video player shown in the introduction as well as more!
	<br/><br/>In this example specifically, you can see the number 6000. This means that the video will start playing and after 6 seconds the video will call the function <code>stopVideo()</code> and the player will stop it. As you can see from the video playing at the top of the website, it does not have this restriction on it because it is able to play throughout the whole video.</left></p>
			<h4>JavaScript</h4>
		<p><left>All of the research I have done shows that using the HTML iFrame code is the easiest and fastest option however there is the JavaScript route as well. In fact the HTML code actually loads the Iframe player API JavaScript code so they make it very convenient when trying to embed a video. In fact you need to have it load this because you have to use JavaScript in order to control the player. The onYouTubeIframeAPIReady function is what is called when the page has finished downloading the JavaScript for the player API.</left></p>
				<br /><div class="blackBar"></div><br />			
		<div class="outer">
			<div id="embedVideo"></div>
				<div class="inner-heading">
				<h2>Video Player: How do you interact with it?</h2>
				<h4>Loading a Video</h4>
				<p><left>Now that we have the basics down we can make adjustments to personalize the video player even more! Here is the code shown in #3 above but posted again to make it easier to follow.</left></p>	
				
				<img src="YouTubeAPILoadingVideoExample.png" alt="YouTubeAPIVideoExample" style="width:400px;height:400px;">

				<div class="inner-body">
				
				<table class="offset">
					<tr>	
						<th>There are two parameters to consider here:</th>
					</tr>
					<td>1. The first parameter specifies either the DOM element of the <code>id</code> or the HTML element</td>
					<tr>
						<td>2. The second parameter specifies the video player options</td>
					</tr>
				</table>
				<p><left>In simpler terms, the first parameter replaces it with the <code>iframe</code> element which contains the player. Keep in mind that this can also change the layout of the page if the parameter replaced has a different display style than the <code>iframe</code>.
				<br/><br/>The second parameter is where all of the personalizing comes in. The object contains 3 main properties:</left></p>
				<table class="offset" border="1">
					<tr>
						<th>Property</th>
						<th>Function</th>
					</tr>
						<td><code class="chunk">width</code></td>
						<td>This is a number and specifies the width of the video player. (Default: 640)</td>
					&lt;/tr&gt;
					<tr>
						<td><code class="chunk">height</code></td>
						<td>This is a number and specifies the height of the video player. (Default: 390)</td>
					</tr>
					<tr>
						<td><code class="chunk">videoId</code></td>
						<td>This is the ID of the video that will play. It can be found at the end of the url. (Ex: for https://www.youtube.com/watch?v=0HTexqxo1og then "0HTexqxo1og" is the ID of the video.</td>
					</tr>
				</table>
				<p><left>The <code>onPlayerReady</code> event ensures that the video will start when the page opens which is shown here by the video in the beginning.</left></p>
				
			<div id="queueFunctions"></div>

				<h2>Functions</h2>
				<h4>Queueing Functions</h4>
				
				<p><left>Now that we can get our video up and running what if we want to not play it immediately? For example wait 5 seconds to start the video. This is where functions come in. We will only touch briefly on this because it the information on this goes into great detail and we are looking more at the main idea.
				<br/><br/>There are 2 types of syntax that make this happen.</left></p>
				
				<h4><li>Argument syntax</li><h4>
				<code>
				 loadVideoById("bHQqvYy5KYo", 5, "large")
			     </code>
				<br/>
				<h4><li>Object syntax</li></h4>
			     <code>
			     loadVideoById({'videoId': 'bHQqvYy5KYo',
               'startSeconds': 5,
               'endSeconds': 60,
               'suggestedQuality': 'large'});
		     </code>
		     <p><left>The API supports the two different types of syntax. The first type, argument syntax, requires that the function arguments be listed in order. The second type, object syntax, lets you pass an object as a single parameter to define the properties and may support additional things that the argument syntax does not.
		     <br/><br/>
		     If you want to start the video 5 seconds in and not end it at a certain time then argument syntax is the way to go. If you want to start the video 5 seconds in and end it after 60 seconds then object syntax gives the option to do that.</left></p>
		     <h4>Functions</h4>
		     <p><left>Without going into too much detail, a brief overview of other functions available include the following. Keep in mind that each of these also have options for argument syntax as well as object syntax.</left></p>
		     
		     <table class="offset" border="1">
					<tr>
						<th>Function</th>
						<th>Description</th>
					</tr>
						<td><code class="chunk">cueVideoById</code></td>
						<td>This function loads the video’s thumbnails and prepares the player to play the video</td>
					&lt;/tr&gt;
					<tr>
						<td><code class="chunk">loadVideoById</code></td>
						<td>This function loads and plays the specified video</td>
					</tr>
					<tr>
						<td><code class="chunk">cueVideoByUrl</code></td>
						<td>This function does the same this as cueVideoById but uses an URL</td>
					</tr>
					<tr>
						<td><code class="chunk">loadVideoByUrl</code></td>
						<td>This function does the same thing as loadVideoById but uses an URL</td>
					</tr>
				</table>	
				<p><left>You can even make functions for playlists! Both of the following functions allow you to play a playlist of videos. Each work a little differently and therefore have different properties.</left></p>
				
		     <table class="offset" border="1">
					<tr>
						<th>Function</th>
						<th>Code</th>
						<th>Description</th>
					</tr>
						<td><code class="chunk">cuePlaylist</code></td>
						<td><code>player.cuePlaylist(playlist:String|Array,
                  				 index:Number,
                 				  startSeconds:Number,
						   suggestedQuality:String):Void</code></td>
						<td>This function queues the specified playlist. It takes an array of YouTube video IDs and an optional parameter to play the first video in the playlist. Again you can customize it with the <code>startSeconds</code> and <code>suggestedQuality</code></td>
					<tr>
						<td><code class="chunk">loadPlaylist</code></td>
						<td><code>player.loadPlaylist(playlist:String|Array,
               				        index:Number,
    				                startSeconds:Number,
				         	suggestedQuality:String):Void</code></td>
						<td>This function loads the specified playlist and plays it. Again it takes an array of video ID’s with the optional parameter with <code>startSeconds</code> and <code>suggestedQuality</code>.</td>
					</tr>
				</table>
				<div id="playbackControls"></div>

				<h2>Playback Controls</h2>
				<br/>
				<h4>Playing a Video</h4>
				<p><left>Up until now we have talked about getting the player set up with basic functions. Now we want to look at ways to customize how it plays the video. There are a lot of different options here. We also can look at what the final player state is after the function executes.</left></p>
				<table class="offset" border="1">
					<tr>
						<th>Function</th>
						<th>Description</th>
						<th>Final Player State</th>
					</tr>
						<td><code class="chunk">player.playVideo():Void</code></td>
						<td>Plays the currently cued video</td>
						<td><code>playing</code>(1)</td>
					<tr>
						<td><code class="chunk">player.pauseVideo():Void</code></td>
						<td>Pauses the currently playing video</td>
						<td><code>paused</code>(2)</td>
					</tr>
					<tr>
						<td><code class="chunk">player.stopVideo():Void</code></td>
						<td>Stops video and stops loading of the video. Warning: This function is not used often and should only be used when you know the user will not be watching any additional videos in the player</td>
						<td>Can put the player into any non-playing state</td>
					</tr>
				</table>
				<h4>Playing a video - Playlist</h4>
				<table class="offset" border="1">
					<tr>
						<th>Function</th>
						<th>Description</th>
					</tr>
						<td><code class="chunk">player.nextVideo():Void</code></td>
						<td>This function loads and plays the next video in the playlist. It can even be set to continuously loop or just end</td>
					<tr>
						<td><code class="chunk">player.previousVideo():Void</code></td>
						<td>This function load and plays the previous video in the playlist. Again can be set to a loop</td>
					</tr>
						<td><code class="chunk">player.playVideoAt(index:Number):Void</code></td>
						<td>This function loads and plays the specified video in the playlist. Keep in mind you have to include an index parameter because you have to specify the index of the video that you want to play</td>
				</table>
				
				<p><left>There are many more ways to personalize the video player but here are a few generally listed:</left></p>
				<table class="offset">
				<tr>
					<th>Changing the Player Volume</th>
				</tr>
					<td>1. <code>player.mute():Void</code></td>
				<tr>
					<td>2. <code>player.unMute():Void</code></td>
				</tr>
					<td>3. <code>player.isMuted():Boolean</code></td>
				<tr>
					<td>4. <code>player.setVolume(volume:Number):Void</code></td>
				</tr>
					<td>5. <code>player.getVolume():Number</code></td>
				</table>
				
				<table class="offset">
				<tr>
					<th>Setting the player size</th>
				</tr>
					<td>1. <code>player.setSize(width:Number, height:Number):Object</code></td>
				</table>
				<table class="offset">
				<tr>
					<th>Setting the playback rate</th>
				</tr>
					<td>1. <code>player.getPlaybackRate():Number</code></td>
				</table>
				
				<h4>Playing a video - Playback Status</h4>
				<p><left>Often the functions return a status which usually comes in the form of a number. Here are the possible values and what they mean.</left></p>
				<li>-1 – unstarted</li>
				<li>0 – ended</li>
				<li>1 – playing</li>
				<li>2 – paused</li>
				<li>3 – buffering</li>
				<li>5 – video cued<li>	
				
		<!-- Events -->	
		<div class="outer">
			<div id="eventsPage"></div>
				<div class="inner-heading">	
					<h3><br />Event Handlers<br /><br /></h3>
				</div>
				<table class="offset" border="1">
							
				<p><left>Last thing to address is Events. At this point you should have a good understanding on how to get everything set up and personalized. There are many different types of events, all however are equally important.</left></p>

				<table border="1">
					<tr>
					<th>Event Handlers</th>
					<th>Description</th>
					</tr>
					<tr>
						<td><code class="chunk">onReady</code></td>
						<td><code>onReady</code> This event fires when a player has finished loading. A good example is playing the video automatically. As you can tell from the video when this website loaded, it has been coded with the onReady event.</td>


					</tr>
					<tr>
						<td><code class="chunk">onPlaybackQualityChange</code></td>
						<td>This event fires when the video playback quality changes. The data property value possible values are:
						<ul>
							<li>small</li>
							<li>medium</li>
							<li>large</li>
							<li>hd720</li>
							<li>hd1080</li>
							<li>highres</li>
						</ul>
						</td>
					</tr>
					<tr>
						<td><code class="chunk">onPlaybackRateChange</code></td>
						<td>This event fires whenever the video playback rate changes</td>
					</tr>
					<tr>
						<td><code class="chunk">onError</code></td>
						<td>This event fires if an error occurs in the player. Here are a few possible errors that could occur:
						<ul>
							<li><b>2</b> - if the request contains an invalid parameter value</li>
							<li><b>5</b> - any error associated with HTML5, such as the HTML5 player not supporting the video</li>
							<li><b>100</b> - the video requested was not found</li>
							<li><b>101</b> - the owner of the video does not allow it to be played in an embedded player</li>
							<li><b>150</b> - the error is the same as <b>101</b></li>
						</ul>
						</td>
					</tr>
				</table>
				
				<br />
		
		<div class="outer">
			<div id="exampleVideo"></div>
				<div class="inner-heading">	
					<h3><br />Example Video<br /><br /></h3>
				</div>
				<div class="inner-body">
				
				<center><div id="playerDiv"></div>
				<p><left>The example video is shown at the top of the page!</left></p>
				
				<br />
				
				
				
