<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Code Display with Copy Button</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        .code-container {
            position: relative;
            margin-bottom: 20px;
            border: 1px solid #ddd;
            border-radius: 4px;
        }
        .code-container pre {
            background: #f5f5f5;
            padding: 15px;
            margin: 0;
            overflow-x: auto;
            white-space: pre-wrap;
            border-radius: 4px 4px 0 0;
        }
        .copy-button {
            position: absolute;
            top: 10px;
            right: 10px;
            background-color: #007bff;
            color: white;
            border: none;
            padding: 5px 10px;
            cursor: pointer;
            border-radius: 4px;
        }
        .copy-button:hover {
            background-color: #0056b3;
        }
    </style>
</head>
<body>

    <h1>Code Display Example</h1>

    <div class="code-container">
        <button class="copy-button" onclick="copyToClipboard()">Copy</button>
        <pre><code id="codeBlock">
function greet(name) {
    return `Hello, ${name}!`;
}

console.log(greet('World'));
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
