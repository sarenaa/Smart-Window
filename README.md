# Smart Window Web Controller

This is a simple web page with an On/Off toggle button to control a smart window's status.

## Features

- Responsive toggle switch
- Real-time display of window status ("ON" or "OFF")
- Easy to integrate with backend APIs or IoT devices

## Code

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Smart Window Control</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f0f4f8;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }

    .container {
      text-align: center;
    }

    h1 {
      color: #333;
    }

    .toggle-switch {
      position: relative;
      width: 80px;
      height: 40px;
      margin: 20px auto;
    }

    .switch {
      position: absolute;
      cursor: pointer;
      width: 100%;
      height: 100%;
      background-color: #ccc;
      border-radius: 40px;
      transition: background-color 0.3s;
    }

    .switch::before {
      content: "";
      position: absolute;
      width: 36px;
      height: 36px;
      left: 2px;
      top: 2px;
      background-color: white;
      border-radius: 50%;
      transition: transform 0.3s;
    }

    input:checked + .switch {
      background-color: #4caf50;
    }

    input:checked + .switch::before {
      transform: translateX(40px);
    }

    .status {
      margin-top: 10px;
      font-size: 1.2em;
      color: #555;
    }

    input {
      display: none;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Smart Window Control</h1>
    <label class="toggle-switch">
      <input type="checkbox" id="windowToggle" />
      <span class="switch"></span>
    </label>
    <div class="status" id="statusText">Window is OFF</div>
  </div>

  <script>
    const toggle = document.getElementById('windowToggle');
    const statusText = document.getElementById('statusText');

    toggle.addEventListener('change', function() {
      statusText.textContent = this.checked ? 'Window is ON' : 'Window is OFF';
    });
  </script>
</body>
</html>
