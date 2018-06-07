 <!DOCTYPE hmtl>
<hmtl>

<head>
    
<title>Afstand berekenen</title>
<meta name="viewport" content="width=device-width, initial-scale=1">
    <meta charset="utf-8">
    <title></title>
    <meta name="Alex&Silas" content="Site">
</head>
    <style type="text/css">

        }
        .invoer{
            margin-left:750px;
            position: relative;
        }
        .Formula{
            background-color: cadetblue;
            border-radius: 5px;
            
        }
        .Given{
            background-color: cadetblue;
            border-radius: 5px;
        }
    </style>

    
<body>
<h2>Hoe bereken je de afstand van bliksem?</h2>
<p1>Om de asftand van bliksem te berekenen heb je de volgende gegeven nodig:               <ol class= "Given">
        <li>De snelheid van het geluid: <b>340</b> meter per seconde. </li>
    <li>De <b>verstreken</b> tijd tussen de <b>flits</b> en <b>donder</b>.(Begin met tellen wanneer je de flits ziet en stop als je de donder hoort). </li>
    </ol> </p1>
<p2>Vervolgens kan je de afstand berekenen met de volgende formule: s= v*t.
    <ul class= "Formula">
        <li>"s" is de <b>afstand</b>.</li>
        <li>"v" is de <b>snelheid</b>.</li>
        <li>"t" is de <b>afstand</b>.</li>
    </ul></p2>
<p3><mark>VOORBEELD</mark> </p3>
<p4><br>Je bent gaan tellen vanaf het moment dat je de flits zag, 7 seconden. </p4>
    

<p id="SpeedOfSound"></p>
    
    
    
    
    <body onload="show();">
	<div>Time: <span id="time"></span></div>
	<input type="button" value="start" onclick="start();">
	<input type="button" value="stop" onclick="stop();">
	<input type="button" value="reset" onclick="reset()">
    
    
<script type="text/javascript">
        var	clsStopwatch = function() {
		// Private vars
		var	startAt	= 0;	// Time of last start / resume. (0 if not running)
		var	lapTime	= 0;	// Time on the clock when last stopped in milliseconds

		var	now	= function() {
				return (new Date()).getTime(); 
			}; 
 
		// Public methods
		// Start or resume
		this.start = function() {
				startAt	= startAt ? startAt : now();
			};

		// Stop or pause
		this.stop = function() {
				// If running, update elapsed time otherwise keep it
				lapTime	= startAt ? lapTime + now() - startAt : lapTime;
				startAt	= 0; // Paused
			};

		// Reset
		this.reset = function() {
				lapTime = startAt = 0;
			};

		// Duration
		this.time = function() {
				return lapTime + (startAt ? now() - startAt : 0); 
			};
	};

var x = new clsStopwatch();
var $time;
var clocktimer;

function pad(num, size) {
	var s = "0000" + num;
	return s.substr(s.length - size);
}

function formatTime(time) {
	var h = m = s = ms = 0;
	var newTime = '';

	h = Math.floor( time / (60 * 60 * 1000) );
	time = time % (60 * 60 * 1000);
	m = Math.floor( time / (60 * 1000) );
	time = time % (60 * 1000);
	s = Math.floor( time / 1000 );
	ms = time % 1000;

	newTime = pad(h, 2) + ':' + pad(m, 2) + ':' + pad(s, 2) + ':' + pad(ms, 3);
	return newTime;
}

function show() {
	$time = document.getElementById('time');
	update();
}

function update() {
	$time.innerHTML = formatTime(x.time());
}

function start() {
	clocktimer = setInterval("update()", 1);
	x.start();
}

function stop() {
	x.stop();
	clearInterval(clocktimer);
}

function reset() {
	stop();
	x.reset();
	update();
}
</script>
    
         <br><br> Of gebruik onze rekenmachine. <br>
         <input type="input" name="bereken">
         <button type="button">Bereken!</button>
        
<script type="text/javascript">
    
    var   input = document.getElementById("inPut").value;   
    const SOS = 340;   
       
        function myFunction(input, SOS){
            return input*SOS;
        }
    
    document.getElementById("SpeedOfSound").innerHTML = myFunction(inPut,SOS);

</script>
             

</body>














