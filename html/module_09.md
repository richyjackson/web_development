# Lesson 9: HTML5 APIs and Advanced Features

## Geolocation API

Get the user’s location (requires permission):

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Geolocation Example</title>
</head>
<body>
    <button onclick="getLocation()">Get My Location</button>
    <p id="location"></p>

    <script>
        function getLocation() {
            if (navigator.geolocation) {
                navigator.geolocation.getCurrentPosition(showPosition, showError);
            } else {
                document.getElementById("location").innerHTML = 
                    "Geolocation is not supported by this browser.";
            }
        }

        function showPosition(position) {
            document.getElementById("location").innerHTML = 
                "Latitude: " + position.coords.latitude + 
                "<br>Longitude: " + position.coords.longitude;
        }

        function showError(error) {
            switch(error.code) {
                case error.PERMISSION_DENIED:
                    alert("User denied the request for Geolocation.");
                    break;
                case error.POSITION_UNAVAILABLE:
                    alert("Location information is unavailable.");
                    break;
                case error.TIMEOUT:
                    alert("The request to get user location timed out.");
                    break;
            }
        }
    </script>
</body>
</html>
```

## Local Storage

Store data in the browser permanently:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Local Storage Example</title>
</head>
<body>
    <input type="text" id="nameInput" placeholder="Enter your name">
    <button onclick="saveName()">Save</button>
    <button onclick="loadName()">Load</button>
    <button onclick="deleteName()">Delete</button>
    <p id="output"></p>

    <script>
        function saveName() {
            const name = document.getElementById("nameInput").value;
            localStorage.setItem("userName", name);
            alert("Name saved!");
        }

        function loadName() {
            const name = localStorage.getItem("userName");
            if (name) {
                document.getElementById("output").innerHTML = "Hello, " + name;
            } else {
                document.getElementById("output").innerHTML = "No name found";
            }
        }

        function deleteName() {
            localStorage.removeItem("userName");
            alert("Name deleted!");
        }
    </script>
</body>
</html>
```

### Local Storage vs Session Storage

```javascript
// Local Storage - persists forever
localStorage.setItem("key", "value");
localStorage.getItem("key");
localStorage.removeItem("key");
localStorage.clear(); // Clear all

// Session Storage - deleted when browser closes
sessionStorage.setItem("key", "value");
sessionStorage.getItem("key");
sessionStorage.removeItem("key");
sessionStorage.clear();
```

## Drag and Drop API

Make elements draggable:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Drag and Drop</title>
    <style>
        #div1, #div2 {
            width: 200px;
            height: 200px;
            padding: 10px;
            border: 1px solid black;
            margin: 10px;
            display: inline-block;
        }
        #drag1 {
            width: 100px;
            height: 100px;
            background-color: red;
            cursor: move;
        }
    </style>
</head>
<body>
    <h2>Drag the red box</h2>
    
    <div id="div1" ondrop="drop(event)" ondragover="allowDrop(event)">
        <div id="drag1" draggable="true" ondragstart="drag(event)"></div>
    </div>
    
    <div id="div2" ondrop="drop(event)" ondragover="allowDrop(event)"></div>

    <script>
        function allowDrop(ev) {
            ev.preventDefault();
        }

        function drag(ev) {
            ev.dataTransfer.setData("text", ev.target.id);
        }

        function drop(ev) {
            ev.preventDefault();
            var data = ev.dataTransfer.getData("text");
            ev.target.appendChild(document.getElementById(data));
        }
    </script>
</body>
</html>
```

## Canvas API

Draw graphics dynamically:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Canvas Example</title>
</head>
<body>
    <canvas id="myCanvas" width="400" height="400" style="border:1px solid #000;">
        Your browser does not support the canvas element.
    </canvas>

    <script>
        const canvas = document.getElementById('myCanvas');
        const ctx = canvas.getContext('2d');

        // Draw rectangle
        ctx.fillStyle = 'blue';
        ctx.fillRect(50, 50, 100, 100);

        // Draw circle
        ctx.beginPath();
        ctx.arc(250, 100, 50, 0, 2 * Math.PI);
        ctx.fillStyle = 'red';
        ctx.fill();

        // Draw line
        ctx.beginPath();
        ctx.moveTo(50, 200);
        ctx.lineTo(350, 200);
        ctx.strokeStyle = 'green';
        ctx.lineWidth = 5;
        ctx.stroke();

        // Draw text
        ctx.font = '30px Arial';
        ctx.fillStyle = 'black';
        ctx.fillText('Hello Canvas!', 100, 300);
    </script>
</body>
</html>
```

## Web Workers

Run JavaScript in background threads:

```html
<!-- index.html -->
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Web Workers</title>
</head>
<body>
    <p>Count: <span id="result">0</span></p>
    <button onclick="startWorker()">Start Worker</button>
    <button onclick="stopWorker()">Stop Worker</button>

    <script>
        let worker;

        function startWorker() {
            if (typeof(Worker) !== "undefined") {
                if (typeof(worker) == "undefined") {
                    worker = new Worker("worker.js");
                }
                worker.onmessage = function(event) {
                    document.getElementById("result").innerHTML = event.data;
                };
            } else {
                alert("Web Workers are not supported in your browser.");
            }
        }

        function stopWorker() {
            if (worker) {
                worker.terminate();
                worker = undefined;
            }
        }
    </script>
</body>
</html>
```

```javascript
// worker.js
let i = 0;

function timedCount() {
    i++;
    postMessage(i);
    setTimeout(timedCount, 500);
}

timedCount();
```

## Web Notifications API

Show desktop notifications:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Notifications</title>
</head>
<body>
    <button onclick="notifyMe()">Notify Me</button>

    <script>
        function notifyMe() {
            if (!("Notification" in window)) {
                alert("This browser does not support notifications");
            } else if (Notification.permission === "granted") {
                new Notification("Hello!", {
                    body: "This is a notification",
                    icon: "icon.png"
                });
            } else if (Notification.permission !== "denied") {
                Notification.requestPermission().then(function(permission) {
                    if (permission === "granted") {
                        new Notification("Permission granted!");
                    }
                });
            }
        }
    </script>
</body>
</html>
```

## History API

Manipulate browser history:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>History API</title>
</head>
<body>
    <button onclick="goBack()">Go Back</button>
    <button onclick="goForward()">Go Forward</button>
    <button onclick="pushState()">Push State</button>

    <script>
        function goBack() {
            window.history.back();
        }

        function goForward() {
            window.history.forward();
        }

        function pushState() {
            history.pushState({page: 1}, "title 1", "?page=1");
        }

        // Listen for state changes
        window.addEventListener('popstate', function(event) {
            console.log("State changed:", event.state);
        });
    </script>
</body>
</html>
```

## Fullscreen API

Make elements fullscreen:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Fullscreen API</title>
    <style>
        #myDiv {
            width: 300px;
            height: 200px;
            background-color: lightblue;
            padding: 20px;
        }
        #myDiv:fullscreen {
            background-color: darkblue;
            color: white;
        }
    </style>
</head>
<body>
    <div id="myDiv">
        <p>Click the button to make this div fullscreen</p>
        <button onclick="openFullscreen()">Go Fullscreen</button>
    </div>

    <script>
        function openFullscreen() {
            const elem = document.getElementById("myDiv");
            if (elem.requestFullscreen) {
                elem.requestFullscreen();
            } else if (elem.webkitRequestFullscreen) { // Safari
                elem.webkitRequestFullscreen();
            } else if (elem.msRequestFullscreen) { // IE11
                elem.msRequestFullscreen();
            }
        }

        // Exit fullscreen
        function closeFullscreen() {
            if (document.exitFullscreen) {
                document.exitFullscreen();
            } else if (document.webkitExitFullscreen) {
                document.webkitExitFullscreen();
            } else if (document.msExitFullscreen) {
                document.msExitFullscreen();
            }
        }
    </script>
</body>
</html>
```

## Content Editable

Make any element editable:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Content Editable</title>
    <style>
        .editable {
            border: 1px solid #ccc;
            padding: 10px;
            min-height: 100px;
        }
    </style>
</head>
<body>
    <h2>Edit this content:</h2>
    <div class="editable" contenteditable="true">
        This text is editable. Click and start typing!
    </div>

    <button onclick="getContent()">Get Content</button>
    <button onclick="clearContent()">Clear</button>

    <script>
        function getContent() {
            const content = document.querySelector('.editable').innerHTML;
            alert(content);
        }

        function clearContent() {
            document.querySelector('.editable').innerHTML = '';
        }
    </script>
</body>
</html>
```

## Media Capture

Access camera and microphone:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Camera Access</title>
</head>
<body>
    <video id="video" width="400" height="300" autoplay></video>
    <button onclick="startCamera()">Start Camera</button>
    <button onclick="stopCamera()">Stop Camera</button>

    <script>
        let stream;

        async function startCamera() {
            try {
                stream = await navigator.mediaDevices.getUserMedia({ 
                    video: true, 
                    audio: false 
                });
                document.getElementById('video').srcObject = stream;
            } catch (err) {
                console.error("Error accessing camera:", err);
                alert("Could not access camera");
            }
        }

        function stopCamera() {
            if (stream) {
                stream.getTracks().forEach(track => track.stop());
            }
        }
    </script>
</body>
</html>
```

## Battery Status API

Check device battery:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Battery Status</title>
</head>
<body>
    <button onclick="getBatteryInfo()">Check Battery</button>
    <div id="battery"></div>

    <script>
        async function getBatteryInfo() {
            if ('getBattery' in navigator) {
                try {
                    const battery = await navigator.getBattery();
                    const output = document.getElementById('battery');
                    output.innerHTML = `
                        Battery Level: ${battery.level * 100}%<br>
                        Charging: ${battery.charging ? 'Yes' : 'No'}<br>
                        Charging Time: ${battery.chargingTime} seconds<br>
                        Discharging Time: ${battery.dischargingTime} seconds
                    `;
                } catch (err) {
                    alert("Error getting battery info");
                }
            } else {
                alert("Battery Status API not supported");
            }
        }
    </script>
</body>
</html>
```

## Best Practices

1. **Check browser support**: Not all APIs work in all browsers
1. **Request permissions properly**: Always handle denials gracefully
1. **Use feature detection**: Check if API exists before using
1. **Provide fallbacks**: Offer alternatives when APIs aren’t supported
1. **Respect user privacy**: Only request necessary permissions
1. **Handle errors**: Always include error handling

## Practice Exercises

1. Create a drawing app using the Canvas API
1. Build a note-taking app using Local Storage
1. Implement drag and drop file upload functionality
1. Create a photo booth app using the Media Capture API
1. Build a notification system for a todo app
1. Make a fullscreen image gallery

## Next Lesson

In Lesson 10, we’ll cover HTML best practices, accessibility, and putting it all together.
