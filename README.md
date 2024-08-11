
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Colorful Code Display with Copy Button</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            background-color: #f0f0f0;
        }
        .code-container {
            position: relative;
            margin-bottom: 20px;
            border: 2px solid #007bff;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            background-color: #fff;
        }
        .code-container pre {
            background: #2e2e2e;
            color: #f8f8f2;
            padding: 15px;
            margin: 0;
            overflow-x: auto;
            border-radius: 8px 8px 0 0;
            font-size: 16px;
            font-family: 'Courier New', Courier, monospace;
        }
        .copy-button {
            position: absolute;
            top: 10px;
            right: 10px;
            background-color: #28a745;
            color: white;
            border: none;
            padding: 8px 15px;
            cursor: pointer;
            border-radius: 4px;
            font-size: 14px;
        }
        .copy-button:hover {
            background-color: #218838;
        }
        .code-container pre code {
            display: block;
            white-space: pre-wrap;
            word-break: break-word;
        }
    </style>
</head>
<body>

    <h1>Colorful Code Display Example</h1>

    <div class="code-container">
        <button class="copy-button" onclick="copyToClipboard()">Copy</button>
        <pre><code id="codeBlock">

        </code></pre>
    </div>

    <script>
        function copyToClipboard() {
            const code = document.getElementById('codeBlock').innerText;
            navigator.clipboard.writeText(code).then(() => {
                alert('Code copied to clipboard!');
            }).catch(err => {
                console.error('Failed to copy code: ', err);
            });
        }
    </script>

</body>
</html>
