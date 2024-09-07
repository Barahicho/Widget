# Widget

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #fce4ec; /* Baby pink background for the page */
        }
        #clock {
            font-family: 'Arial', sans-serif;
            font-size: 72px;
            font-weight: 500;
            color: #6f4f28; /* Brown color for the text */
            background-color: #fce4ec; /* Baby pink background inside the clock */
            padding: 0; /* Remove any padding */
            border: none; /* Remove border */
            box-shadow: none; /* Remove shadow */
            border-radius: 0; /* No rounded corners */
            text-align: center; /* Center text alignment */
        }
    </style>
    <title>Digital Clock</title>
</head>
<body>
    <div id="clock"></div>

    <script>
        function updateClock() {
            const now = new Date();
            let hours = now.getHours();
            const minutes = String(now.getMinutes()).padStart(2, '0');
            const ampm = hours >= 12 ? 'PM' : 'AM';
            hours = hours % 12;
            hours = hours ? hours : 12; // the hour '0' should be '12'
            document.getElementById('clock').textContent = `${hours}:${minutes} ${ampm}`;
        }
        setInterval(updateClock, 60000); // Update every minute
        updateClock(); // Initial call to display clock immediately
    </script>
</body>
</html>
