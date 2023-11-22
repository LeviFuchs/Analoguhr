# Analoguhr
# Analoguhr
# Analoguhr
# Analoguhr
# Analoguhr

/* Restoring browser effects */
* { 
    margin: 0; 
    padding: 0; 
    box-sizing: border-box; 
    ; 
} 
  
/* All of the same styling to the body */
body { 
    height: 100vh; 
    display: flex; 
    justify-content: center; 
    align-items: center; 
    background-color: #000; 
    background-image: linear-gradient( 
            70deg, black, white); 
} 
  
/* Sizing, positioning of main  
    dial of the clock */

.clock {
    width: 80vw; /* 80% of the viewport width */
    max-width: 25em; /* Maximum width of 25em */
    height: 80vw; /* 80% of the viewport width */
    max-height: 25em; /* Maximum height of 25em */
    background-image: url(R.png);
    background-size: cover;
    box-shadow: 0 3vw 5.8vw; /* 3% of the viewport width for horizontal and vertical shadow */
    border-radius: 50%; /* Use percentage for border-radius to make it circular */
}
  
.hand.hour-hand, 
.hand.min-hand, 
.hand.second-hand { 
    width: 1%; 
    position: absolute; 
    top: 50%; 
    left: 50%; 
    transform: translate(-50%, -100%); 
    transform-origin: bottom; 
    z-index: 2; 
    border-radius: 2em; 
} 
  

  
/* Different length of different hands of clock */
.hand.hour-hand { 
    height: 25%; 
    background-color: #000000; 
} 
  
.hand.min-hand { 
    height: 30%; 
    background-color: #000000; 
} 
  
.hand.second-hand { 
    height: 40%; 
    background-color: #ff0000; 
    transform-origin: 50% 85%; 
} 




// Selecting all of the css classes on which 
// we want to apply functionalities 
const hr = document.querySelector('.hand.hour-hand') 
const min = document.querySelector('.hand.min-hand') 
const sec = document.querySelector('.hand.second-hand') 

// Setting up the period of working 
setInterval(() => { 

	// Extracting the current time 
	// from DATE() function 
	let day = new Date() 
	let hour = day.getHours() 
	let minutes = day.getMinutes() 
	let seconds = day.getSeconds() 

	// Formula that is explained above for 
	// the rotation of different hands 
	let hrrotation = (30 * hour) + (0.5 * minutes); 
	let minrotation = 6 * minutes; 
	let secrotation = 6 * seconds; 

	hr.style.transform = 
		`translate(-50%,-100%) rotate(${hrrotation}deg)` 
	min.style.transform = 
		`translate(-50%,-100%) rotate(${minrotation}deg)` 
	sec.style.transform = 
		`translate(-50%,-85%) rotate(${secrotation}deg)` 
});