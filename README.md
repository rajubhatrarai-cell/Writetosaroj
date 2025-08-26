<!DOCTYPE html>
<html>
<head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>WriteToSaroj 💌</title>
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background: #ffdee9;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .app {
            background: #fff0f5;
            width: 350px;
            max-width: 95%;
            border-radius: 20px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.2);
            display: flex;
            flex-direction: column;
            overflow: hidden;
        }

        .header {
            background: #ff69b4;
            color: white;
            text-align: center;
            padding: 15px;
            font-size: 1.2em;
        }

        .login, .chat {
            padding: 20px;
            display: flex;
            flex-direction: column;
        }

        input, textarea {
            margin: 5px 0;
            padding: 10px;
            border-radius: 10px;
            border: 1px solid #ff69b4;
            font-size: 1em;
        }

        button {
            background: #ff69b4;
            color: white;
            border: none;
            padding: 10px;
            margin-top: 10px;
            border-radius: 10px;
            cursor: pointer;
            font-weight: bold;
            font-size: 1em;
        }

        button:hover {
            background: #ff1493;
        }

        .messages {
            background: #ffe4e1;
            border-radius: 10px;
            padding: 10px;
            height: 150px;
            overflow-y: auto;
            margin-top: 10px;
        }

        .message {
            background: #ffc0cb;
            padding: 8px;
            border-radius: 8px;
            margin: 5px 0;
        }
    </style>
</head>
<body>

<div class="app">
    <div class="header">WriteToSaroj 💌</div>

    <!-- Login Form -->
    <div class="login" id="loginDiv">
        <input type="text" id="username" placeholder="Username">
        <input type="password" id="password" placeholder="Password">
        <button onclick="showChat()">Login / Sign Up</button>
    </div>

    <!-- Chat Interface -->
    <div class="chat" id="chatDiv" style="display:none;">
        <textarea id="messageInput" rows="3" placeholder="Write your message here..."></textarea>
        <button onclick="sendToGmail()">Send 💌</button>
        <div class="messages">
            <div class="message">Hi Saroj! 💖</div>
            <div class="message">Hello! 🌸</div>
        </div>
        <button onclick="logout()">Logout</button>
    </div>
</div>

<script>
function showChat(){
    document.getElementById('loginDiv').style.display = 'none';
    document.getElementById('chatDiv').style.display = 'flex';
}

function logout(){
    document.getElementById('loginDiv').style.display = 'flex';
    document.getElementById('chatDiv').style.display = 'none';
    document.getElementById('username').value = '';
    document.getElementById('password').value = '';
    document.getElementById('messageInput').value = '';
}

// Gmail send function using mailto
function sendToGmail(){
    const message = document.getElementById('messageInput').value.trim();
    if(!message) return alert("Please write a message!");
    const subject = encodeURIComponent("Message from WriteToSaroj");
    const body = encodeURIComponent(message);
    const email = "rajubhatrarai@gmail.com";
    window.location.href = `mailto:${email}?subject=${subject}&body=${body}`;
    document.getElementById('messageInput').value = '';
}
</script>

</body>
</html>