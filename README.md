<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Google-like Search Interface</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Roboto', sans-serif;
            background-color: #f2f2f2;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
        }
        .logo {
            margin-bottom: 30px;
            max-width: 300px; /* Limit logo size for better appearance */
        }
        .search-container {
            width: 100%;
            max-width: 700px; /* Increased max width for a larger search bar */
            display: flex;
            justify-content: center;
            align-items: center;
            border-radius: 24px;
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.2);
            background-color: white;
            padding: 10px;
        }
        .search-input {
            width: 100%;
            border: 1px solid #ddd; /* Add border for better visibility */
            outline: none;
            padding: 12px; /* Increased padding for a more comfortable input area */
            font-size: 18px; /* Increased font size for better readability */
            border-radius: 24px;
        }
        .search-button {
            padding: 12px 24px; /* Increased button padding */
            border: none;
            border-radius: 24px;
            background-color: #007BFF;
            color: white;
            font-size: 18px; /* Increased button font size */
            cursor: pointer;
            margin-left: 10px;
            transition: background-color 0.3s;
        }
        .search-button:hover {
            background-color: #0056b3;
        }
        @media (max-width: 768px) {
            .search-container {
                width: 90%; /* Make search container responsive on smaller screens */
            }
        }
    </style>
</head>
<body>

    <img src="https://www.google.com/images/branding/googlelogo/1x/googlelogo_color_272x92dp.png" alt="Google Logo" class="logo" />

    <div class="search-container">
        <input type="text" class="search-input" placeholder="Search Google or type a URL">
        <button class="search-button">Search</button>
    </div>

</body>
</html>
