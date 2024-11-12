<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Link Copier</title>
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
        .link-container {
            margin: 20px auto;
            padding: 15px;
            border-radius: 8px;
            background-color: #fff;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: relative;
            transition: transform 0.2s;
        }
        .link-container:hover {
            transform: translateY(-5px);
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
        }
        .link {
            display: block;
            font-family: 'Courier New', Courier, monospace;
            white-space: nowrap;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            background-color: #f8f8f8;
            margin-bottom: 10px;
            overflow: hidden;
            text-overflow: ellipsis;
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
            .link-container {
                width: 90%;
            }
        }
    </style>
</head>
<body>

    <h1>Link Copier</h1>

    <div id="link-snippets">
        <!-- Links will be generated here -->
    </div>

    <script>
        const links = [
            https://drive.google.com/file/d/18qoWuK28wtl8A_qAWwxDsiG-SWMdr2b1/view?usp=drive_link
        ];

        const linkContainer = document.getElementById('link-snippets');

        links.forEach((link, index) => {
            const linkDiv = document.createElement('div');
            linkDiv.className = 'link-container';

            const linkBlock = document.createElement('div');
            linkBlock.className = 'link';
            linkBlock.textContent = link;

            const copyButton = document.createElement('button');
            copyButton.className = 'copy-button';
            copyButton.textContent = 'Copy';
            copyButton.onclick = () => {
                navigator.clipboard.writeText(link).then(() => {
                    alert('Link copied to clipboard!');
                }).catch(err => {
                    alert('Failed to copy: ' + err);
                });
            };

            linkDiv.appendChild(linkBlock);
            linkDiv.appendChild(copyButton);
            linkContainer.appendChild(linkDiv);
        });
    </script>

</body>
</html>
