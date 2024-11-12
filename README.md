
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Code Snippet Copier</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Roboto', sans-serif;
            background-color: #f4f4f4;
            color: #333;
            margin: 0;
            padding: 20px;
        }
        h1 {
            text-align: center;
            color: #007BFF;
        }
        .code-container {
            margin: 20px auto;
            padding: 15px;
            border-radius: 8px;
            background-color: #fff;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: relative;
            transition: transform 0.2s;
        }
        .code-container:hover {
            transform: translateY(-5px);
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
        }
        .code {
            font-family: 'Courier New', Courier, monospace;
            white-space: pre-wrap;
            background-color: #f8f8f8;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            overflow: auto;
            max-height: 150px;
        }
        .copy-button {
            position: absolute;
            top: 15px;
            right: 15px;
            padding: 8px 12px;
            background-color: #007BFF;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        .copy-button:hover {
            background-color: #0056b3;
        }
        @media (max-width: 600px) {
            .code-container {
                width: 90%;
            }
        }
    </style>
</head>
<body>

    <h1>Code Snippet Copier</h1>

    <div id="code-snippets">
        <!-- Code snippets will be generated here -->
    </div>

    <script>
        const codeSnippets = [
            "console.log('Hello, World!');",
            "function add(a, b) { return a + b; }",
            "const arr = [1, 2, 3, 4, 5];",
            "document.getElementById('myElement').innerHTML = 'Hello';",
            "let x = 10;",
            "const obj = { key: 'value' };",
            "if (x > 5) { console.log('Greater than 5'); }",
            "const promise = new Promise((resolve, reject) => { /*...*/ });",
            "async function fetchData() { /*...*/ }",
            "for (let i = 0; i < 5; i++) { console.log(i); }",
            "const filtered = arr.filter(num => num > 2);",
            "const mapped = arr.map(num => num * 2);",
            "const reduced = arr.reduce((sum, num) => sum + num, 0);",
            "class Person { constructor(name) { this.name = name; } }",
            "const mySet = new Set([1, 2, 3]);",
            "const myMap = new Map(); myMap.set('key', 'value');",
            "const regex = /\\d+/g;",
            "const date = new Date();",
            "const jsonString = JSON.stringify({ name: 'John' });",
            "const parsed = JSON.parse(jsonString);",
            "const xhr = new XMLHttpRequest();"
        ];

        const codeContainer = document.getElementById('code-snippets');

        codeSnippets.forEach((code, index) => {
            const codeDiv = document.createElement('div');
            codeDiv.className = 'code-container';

            const codeBlock = document.createElement('div');
            codeBlock.className = 'code';
            codeBlock.textContent = code;

            const copyButton = document.createElement('button');
            copyButton
