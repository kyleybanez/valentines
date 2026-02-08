<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Will You Be My Valentine?</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #ffe6f2;
            color: #d63384;
            text-align: center;
            padding: 20px;
            margin: 0;
            overflow: hidden; /* Prevents scrolling issues on mobile */
        }
        h1 {
            font-size: 2em;
            margin-bottom: 40px;
        }
        .buttons {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap; /* Allows wrapping on small screens */
        }
        button {
            padding: 15px 30px;
            font-size: 1.2em;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            transition: background-color 0.3s;
            min-width: 120px; /* Ensures buttons are not too small */
        }
        #yes {
            background-color: #ff69b4;
            color: white;
        }
        #yes:hover {
            background-color: #ff1493;
        }
        #no {
            background-color: #ffb3ba;
            color: white;
            position: absolute; /* Allows it to move */
        }
        #no:hover {
            background-color: #ff6b9d;
        }

        /* Media queries for mobile responsiveness */
        @media (max-width: 768px) {
            h1 {
                font-size: 1.5em;
                margin-bottom: 30px;
            }
            button {
                padding: 12px 25px;
                font-size: 1em;
                min-width: 100px;
            }
            .buttons {
                gap: 15px;
            }
        }
        @media (max-width: 480px) {
            h1 {
                font-size: 1.2em;
                margin-bottom: 20px;
            }
            button {
                padding: 10px 20px;
                font-size: 0.9em;
                min-width: 80px;
            }
            .buttons {
                gap: 10px;
            }
        }
    </style>
</head>
<body>
    <h1>Will You Be My Valentine? 💖</h1>
    <div class="buttons">
        <button id="yes">Yes</button>
        <button id="no">No</button>
    </div>

    <script>
        const noButton = document.getElementById('no');
        const yesButton = document.getElementById('yes');

        // Function to move the "No" button to a random position within bounds
        function moveNoButton() {
            const maxX = window.innerWidth - noButton.offsetWidth - 20; // Leave some margin
            const maxY = window.innerHeight - noButton.offsetHeight - 20;
            const randomX = Math.max(0, Math.random() * maxX); // Ensure it doesn't go off-screen left/top
            const randomY = Math.max(0, Math.random() * maxY);
            noButton.style.left = randomX + 'px';
            noButton.style.top = randomY + 'px';
        }

        // Move the button on hover (PC), click, or touch (mobile)
        noButton.addEventListener('mouseover', moveNoButton);
        noButton.addEventListener('click', moveNoButton);
        noButton.addEventListener('touchstart', moveNoButton); // For mobile touch

        // "Yes" button action
        yesButton.addEventListener('click', () => {
            alert('Yay! You said yes! Happy Valentine\'s Day! ❤️');
            // You can replace this with something else, like window.location.href = 'another-page.html';
        });
    </script>
</body>
</html>
