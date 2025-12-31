# song
the is the code for song typing delay by 0.8sec

<!DOCTYPE html>
<html lang="hi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>तुमसा कोई प्यारा - Typing Effect</title>
    <style>
        body {
            font-family: 'Noto Sans Devanagari', 'Courier New', monospace;
            background: linear-gradient(135deg, #1a1a2e, #16213e);
            color: #ff6b9d;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
            padding: 20px;
        }
        .typing-container {
            font-size: 28px;
            max-width: 800px;
            line-height: 1.6;
            border-right: 3px solid #ff6b9d;
            white-space: pre-wrap;
            overflow: hidden;
            animation: blink 1s infinite;
            text-shadow: 0 0 10px rgba(255, 107, 157, 0.5);
        }
        @keyframes blink {
            0%, 50% { border-color: #ff6b9d; }
            51%, 100% { border-color: transparent; }
        }
        @media (max-width: 768px) {
            .typing-container { font-size: 20px; }
        }
    </style>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Devanagari:wght@400;700&display=swap" rel="stylesheet">
</head>
<body>
    <div class="typing-container" id="songText"></div>

    <script>
        const songLyrics = `तुमसा कोई प्यारा कोई मासूम नही है
क्या चीज़ हो तुम खुद तुम्हे मालूम नही है
तुमसा कोई प्यारा कोई मासूम नही है
क्या चीज़ हो तुम खुद तुम्हे मालूम नही है
सो फूल खिले जब ये खिला रूप सुनहरा
सो चाँद बने जब ये बना चाँद सा चेहरा
सो फूल खिले जब ये खिला रूप सुनहरा
सो चाँद बने जब ये बना चाँद सा चेहरा`;

        const typingDelay = 80; // 0.8 * 100 = 80ms per character
        const element = document.getElementById('songText');

        function typeWriter(text, index = 0) {
            if (index < text.length) {
                element.textContent += text.charAt(index);
                setTimeout(() => typeWriter(text, index + 1), typingDelay);
            }
        }

        window.addEventListener('load', () => {
            typeWriter(songLyrics);
        });
    </script>
</body>
</html>
