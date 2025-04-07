<!DOCTYPE html>
<html>
<head>
    <title>Instagram Downloader</title>
</head>
<body>
    <h1>Instagram Downloader</h1>
    <form method="POST">
        <input type="text" name="url" placeholder="Paste Instagram URL here" required>
        <button type="submit">Download</button>
    </form>
    {% if url %}
        <h2>Download Options for: {{ url }}</h2>
        <ul>
            {% for tag in hashtags %}
                <li>{{ tag }}</li>
            {% endfor %}
        </ul>
    {% endif %}
</body>
</html>
