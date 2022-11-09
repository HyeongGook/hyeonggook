<!DOCTYPE html>
<html lang="en">
  <head>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/0.10.2/p5.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/0.10.2/addons/p5.sound.min.js"></script>
    <meta charset="utf-8" />
  </head>
  <body
    style="
      background-color: black;
      margin-top: 10%;
      justify-content: center;
      align-items: center;
      text-align: center;
    "
  >
    <script>
      let x, y;
      let minutesRadius = radius * 0.6;
      let hoursRadius = radius * 0.5;

      function setup() {
        createCanvas(710, 400);
        //strokeWeight(20.0);
        //stroke(255, 100);
      }

      function draw() {
        background(0);
        fill(255, 255, 255);
        ellipse(355, 200, 300);
        fill(0, 0, 0);
        rect(355 - 70 - 40, 120 - 5, 80, 10, 5, 5, 5, 5);
        rect(355 + 70 - 40, 120 - 5, 80, 10, 5, 5, 5, 5);
        circle(355, 200, 10);
        rect(355 - 20, 200 + 30, 40, 10, 5, 5, 5, 5);

        x = mouseX;
        if (x < 315) {
          x = 315;
        } else if (x > 365) {
          x = 365;
        }
        y = mouseY;
        if (y < 115) {
          y = 115;
        } else if (y > 145) {
          y = 145;
        }

        rect(x - 70, y, 30, 30, 5, 5, 20, 20);
        rect(x + 70, y, 30, 30, 5, 5, 20, 20);

        noStroke();
        fill(255, 111, 105);
        circle(
          355 + sin((hour() / 12) * TWO_PI) * 180,
          200 - cos((hour() / 12) * TWO_PI) * 175,
          12
        );
        fill(255, 204, 92);
        circle(
          355 + sin((minute() / 60) * TWO_PI) * 170,
          200 - cos((minute() / 60) * TWO_PI) * 165,
          12
        );
        fill(136, 216, 176);
        circle(
          355 + sin((second() / 60) * TWO_PI) * 160,
          200 - cos((second() / 60) * TWO_PI) * 155,
          12
        );
      }
    </script>
  </body>
</html>
