<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Eureka Project</title>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/github-markdown-css/github-markdown.min.css">
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      line-height: 1.6;
    }
    .markdown-body {
      box-sizing: border-box;
      min-width: 200px;
      max-width: 980px;
      margin: auto;
      padding: 20px;
    }
  </style>
</head>
<body>
  <div id="content" class="markdown-body"></div>

  <script>
    // README.md 파일 내용을 가져오기
    fetch("README.md")
      .then(response => response.text())
      .then(text => {
        // markdown을 HTML로 변환
        const converter = new showdown.Converter();
        const html = converter.makeHtml(text);
        document.getElementById("content").innerHTML = html;
      })
      .catch(error => {
        console.error("Error loading README.md:", error);
        document.getElementById("content").innerText = "Failed to load README.md";
      });
  </script>
  <script src="https://cdn.jsdelivr.net/npm/showdown/dist/showdown.min.js"></script>
</body>
</html>
