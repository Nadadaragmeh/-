# -<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تحميل الملفات</title>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; padding: 20px; }
        .container { max-width: 500px; margin: auto; padding: 20px; border: 1px solid #ddd; border-radius: 10px; }
        input, textarea, button { display: block; width: 100%; margin: 10px 0; padding: 10px; }
    </style>
</head>
<body>
    <div class="container">
        <h2>تحميل الفيديوهات والصور</h2>
        <textarea id="text" placeholder="اكتب هنا..."></textarea>
        <input type="file" id="file" accept="image/*,video/*">
        <button onclick="upload()">رفع الملف</button>
        <h3>العرض:</h3>
        <div id="output"></div>
    </div>
    
    <script>
        function upload() {
            const text = document.getElementById('text').value;
            const fileInput = document.getElementById('file');
            const output = document.getElementById('output');
            
            if (text) {
                const p = document.createElement('p');
                p.textContent = text;
                output.appendChild(p);
            }
            
            if (fileInput.files.length > 0) {
                const file = fileInput.files[0];
                const url = URL.createObjectURL(file);
                let media;
                
                if (file.type.startsWith('image')) {
                    media = document.createElement('img');
                    media.style.maxWidth = '100%';
                } else if (file.type.startsWith('video')) {
                    media = document.createElement('video');
                    media.controls = true;
                    media.style.maxWidth = '100%';
                }
                
                if (media) {
                    media.src = url;
                    output.appendChild(media);
                }
            }
        }
    </script>
</body>
</html>

رياضيات
