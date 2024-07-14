<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tarsanas Menu</title>
    <style>
        body, html {
            height: 100%;
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: #f8f8f8;
        }
        #menu {
            max-width: 100%;
            max-height: 100%;
            transform-origin: center center;
            transition: transform 0.25s ease;
        }
    </style>
</head>
<body>
    <img id="menu" src="menu.jpg" alt="Tarsanas Menu">
    <script>
        let scale = 1;
        const el = document.getElementById('menu');

        el.addEventListener('wheel', function(e) {
            if (e.deltaY > 0) {
                scale -= 0.1;
            } else {
                scale += 0.1;
            }

            if (scale < 1) {
                scale = 1;
            }

            el.style.transform = `scale(${scale})`;
        });

        el.addEventListener('gesturestart', function(e) {
            e.preventDefault();
        });

        el.addEventListener('gesturechange', function(e) {
            scale = e.scale;
            el.style.transform = `scale(${scale})`;
        });

        el.addEventListener('gestureend', function(e) {
            e.preventDefault();
        });
    </script>
</body>
</html>
