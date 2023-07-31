---
title: JavaScript
date: 2022-07-28 19:04:00 +/-TTTT
categories: [TOP_CATEGORIE, SUB_CATEGORIE]
tags: [TAG]     # TAG names should always be lowercase
img_path: /assets/postsImgs/test
---

<html>
<head>

  <h1>Text Input and Character Counter</h1>
  <input type="text" id="inputBox" oninput="countCharacters()" />
  <p>Character Count: <span id="charCount">0</span></p>

  <script>
    function countCharacters() {
      const inputBox = document.getElementById('inputBox');
      const charCountSpan = document.getElementById('charCount');
      const text = inputBox.value;
      const charCount = text.length;
      charCountSpan.textContent = charCount;
    }
  </script>
  <title>{{ page.title }}</title>
  <!-- Your other head content here -->

  <!-- Include custom JavaScript if specified in the page's front matter -->
  <!-- <script src="js/wc.js"></script> -->

</head>
<body>
  <!-- Your page content here -->
</body>
</html>


<!-- 
<html>
<head>
  <title>Simple JavaScript Animation</title>
  <style>
    #ball {
      width: 50px;
      height: 50px;
      background-color: red;
      border-radius: 50%;
      position: absolute;
    }
  </style>
</head>
<body>
  <div id="ball"></div>
  <script>
    window.onload = function () {
      const ball = document.getElementById('ball');
      const container = document.body;

      let x = 0; // Initial horizontal position
      let y = 0; // Initial vertical position
      let xDirection = 1; // Initial horizontal direction (1 for right, -1 for left)
      let yDirection = 1; // Initial vertical direction (1 for down, -1 for up)
      const speed = 3; // Ball speed in pixels per frame

      function animateBall() {
        // Update the position of the ball
        x += xDirection * speed;
        y += yDirection * speed;

        // Check collision with container's edges
        if (x + ball.clientWidth >= container.clientWidth || x <= 0) {
          xDirection *= -1; // Change horizontal direction when hitting the left or right edge
        }
        if (y + ball.clientHeight >= container.clientHeight || y <= 0) {
          yDirection *= -1; // Change vertical direction when hitting the top or bottom edge
        }

        // Apply the updated position to the ball's style
        ball.style.left = x + 'px';
        ball.style.top = y + 'px';

        // Request the next frame of the animation
        requestAnimationFrame(animateBall);
      }

      // Start the animation
      animateBall();
    };
  </script>
</body>
</html> -->
