# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks

Create a CSS animation.
Store data in localStorage.
Apply JavaScript to trigger animations.

Happy Coding! 💻✨


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Transitions and Animations</title>
    <style>
        /* Basic Styling */
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 50px;
        }

        h1 {
            color: #333;
        }

        /* Button Style */
        #animateButton {
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 5px;
            transition: background-color 0.3s ease;
        }

        #animateButton:hover {
            background-color: #0056b3;
        }

        /* Box to Animate */
        .box {
            width: 100px;
            height: 100px;
            margin-top: 20px;
            background-color: #ff6347;
            border-radius: 10px;
            transition: transform 1s ease, background-color 1s ease;
        }

        /* Animation Class */
        .animate {
            transform: rotate(360deg);
            background-color: #32cd32;
        }

        /* Transition for Color Picker */
        input[type="color"] {
            margin-top: 20px;
            padding: 10px;
            font-size: 16px;
        }
    </style>
</head>
<body>
    <h1>Welcome to the Animation Playground</h1>
    <button id="animateButton">Click Me!</button>
    <div id="animationElement" class="box"></div>

    <label for="colorPicker">Choose Background Color: </label>
    <input type="color" id="colorPicker">
    
    <script>
        // Function to trigger animation on button click
        const animateButton = document.getElementById('animateButton');
        const animationElement = document.getElementById('animationElement');

        // Check if a stored color preference exists and apply it
        const savedColor = localStorage.getItem('backgroundColor');
        if (savedColor) {
            document.body.style.backgroundColor = savedColor;
        }

        // Event Listener to animate the box
        animateButton.addEventListener('click', function() {
            animationElement.classList.toggle('animate');
        });

        // Event Listener to save color preference and update background color
        const colorPicker = document.getElementById('colorPicker');
        colorPicker.addEventListener('input', function() {
            const selectedColor = colorPicker.value;
            localStorage.setItem('backgroundColor', selectedColor);
            document.body.style.backgroundColor = selectedColor;
        });
    </script>
</body>
</html>

