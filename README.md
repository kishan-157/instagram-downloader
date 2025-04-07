from flask import Flask, render_template, request, jsonify

app = Flask(__name__)

@app.route("/", methods=["GET", "POST"])
def index():
    if request.method == "POST":
        url = request.form.get("url")
        return render_template("index.html", url=url, hashtags=["#insta", "#video", "#download"])
    return render_template("index.html")

@app.route("/api/download", methods=["POST"])
def api_download():
    url = request.json.get("url")
    return jsonify({
        "status": "success",
        "content_type": "Reel",
        "qualities": ["144p", "360p", "720p", "1080p"],
        "hashtags": ["#example", "#download"]
    })

if __name__ == "__main__":
    app.run(debug=True)
