<!DOCTYPE html>
<html>
<head>
    <title>Fake News Detection</title>
    <style>
        body {
            font-family: Arial;
            background-color: #f4f4f4;
            text-align: center;
            padding: 40px;
        }
        textarea {
            width: 60%;
            height: 120px;
            padding: 10px;
        }
        button {
            padding: 10px 20px;
            background-color: #007bff;
            color: white;
            border: none;
            cursor: pointer;
        }
        #result {
            margin-top: 20px;
            font-size: 20px;
            font-weight: bold;
        }
    </style>
</head>
<body>

    <h1>Fake News Detection Website</h1>

    <p>Enter news text below:</p>
    <textarea id="newsInput" placeholder="Paste news here..."></textarea>
    <br><br>
    <button onclick="checkNews()">Check News</button>

    <div id="result"></div>

    <script>
        function checkNews() {
            var text = document.getElementById("newsInput").value;
            var result = document.getElementById("result");

            if(text.length < 50) {
                result.innerHTML = "⚠️ Please enter more detailed news content.";
                result.style.color = "orange";
            } else {
                // Simple demo logic
                if(text.toLowerCase().includes("shocking") || text.toLowerCase().includes("100% guaranteed")) {
                    result.innerHTML = "🚨 This news might be FAKE.";
                    result.style.color = "red";
                } else {
                    result.innerHTML = "✅ This news appears more reliable.";
                    result.style.color = "green";
                }
            }
        }
    </script>

</body>
</html>
