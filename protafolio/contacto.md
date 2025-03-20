<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contacto</title>
    <style>
        /* Estilo general */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f0f7f3;
            scroll-behavior: smooth;
            animation: fadeIn 1s ease-in;
        }
        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }

        /* Navbar */
        .navbar {
            background-color: #456B53;
            padding: 15px;
            text-align: center;
            position: fixed;
            width: 100%;
            top: 0;
            left: 0;
            z-index: 1000;
            display: flex;
            justify-content: center;
            transition: background-color 0.3s ease;
        }
        .navbar a {
            color: white;
            margin: 0 15px;
            text-decoration: none;
            font-weight: bold;
            text-transform: uppercase;
            transition: color 0.3s ease;
        }
        .navbar a:hover {
            color: #D3845C;
        }
        #menu-btn {
            display: none;
            font-size: 24px;
            background: none;
            border: none;
            cursor: pointer;
            color: white;
            transition: transform 0.3s ease;
        }
        #menu-btn:hover {
            transform: scale(1.1);
        }
        @media (max-width: 768px) {
            .navbar {
                display: none;
                flex-direction: column;
                background-color: #456B53;
            }
            #menu-btn {
                display: block;
                position: fixed;
                top: 15px;
                right: 15px;
            }
        }

        /* Sección principal */
        .section-container {
            display: flex;
            align-items: center;
            justify-content: center;
            max-width: 1000px;
            margin: 80px auto;
            background-color: #EAF1EB;
            padding: 40px;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            transition: transform 0.5s ease-in-out;
        }
        .section-container:hover {
            transform: scale(1.02);
        }
        .section-text {
            max-width: 500px;
            text-align: center;
        }
        .section-text h2 {
            color: #456B53;
            font-size: 32px;
            margin-bottom: 20px;
            font-weight: bold;
        }
        .section-text p {
            color: #456B53;
            font-size: 18px;
            line-height: 1.6;
        }
        .section-text a {
            color: #D3845C;
            text-decoration: none;
        }
        .section-text a:hover {
            text-decoration: underline;
        }

        /* Estilo de lista */
        #contacto ul {
            list-style-type: none;
            padding: 0;
            margin: 0;
        }
        #contacto li {
            margin: 10px 0;
            font-size: 18px;
        }

        /* Fotografía y créditos */
        .photo-credit {
            font-size: 14px;
            font-style: italic;
            color: #BF7145;
        }

        /* Colores de fondo de las reacciones */
        .color-change-1 {
            background-color: #f5a5d0;
        }
        .color-change-2 {
            background-color: #e1c8e1;
        }
        .color-change-3 {
            background-color: #d1f0c1;
        }

    </style>
</head>
<body>
    <!-- Botón de menú hamburguesa -->
    <button id="menu-btn">☰</button>
    <div class="navbar" id="navbar">
        <a href="index.html">PRINCIPAL</a>
        <a href="habilidades.html">HABILIDADES</a>
        <a href="experiencia.html">EXPERIENCIA LABORAL</a>
        <a href="educacion.html">EDUCACIÓN Y CERTIFICACIONES</a>
        <a href="contacto.html">CONTACTO</a>
    </div>

    <section id="work" class="section-container">
        <div class="section-text">
            <h2>Contacto</h2>
            <section id="contacto">
                <ul>
                    <li><strong>📧 Correo:</strong> <a href="mailto:adan.condori@example.com">adan.condori@example.com</a></li>
                    <li><strong>📞 Teléfono:</strong> <a href="tel:+59170000000">+591 70000000</a></li>
                    <li><strong>📍 Ubicación:</strong> Santa Cruz de la Sierra, Bolivia</li>
                    <li><strong>🔗 LinkedIn:</strong> <a href="https://www.linkedin.com/in/adancondori" target="_blank">linkedin.com/in/adancondori</a></li>
                    <li><strong>📸 Instagram:</strong> <a href="https://www.instagram.com/adan.condori" target="_blank">@adan.condori</a></li>
                    <li><strong>📘 Facebook:</strong> <a href="https://www.facebook.com/adan.condori" target="_blank">@adan.condori</a></li>
                    <li><strong>🐙 GitHub:</strong> <a href="https://github.com/adancondori" target="_blank">github.com/adancondori</a></li>
                </ul>
            </section>
        </div>
    </section>

    <script>
        // JavaScript para mostrar/ocultar el menú
        document.getElementById("menu-btn").addEventListener("click", function () {
            let navbar = document.getElementById("navbar");
            navbar.style.display = navbar.style.display === "flex" ? "none" : "flex";
        });

        // Función para cambiar el color de fondo al hacer clic en las imágenes
        function changeBackgroundColor(colorNumber) {
            var container = document.getElementById("work");
            if (colorNumber === 1) {
                container.className = "section-container color-change-1";
            } else if (colorNumber === 2) {
                container.className = "section-container color-change-2";
            } else if (colorNumber === 3) {
                container.className = "section-container color-change-3";
            }
        }

        // Función para cargar contenido dinámico de la sección de contacto
        function loadContact() {
            var xhr = new XMLHttpRequest();
            xhr.open('GET', 'contacto-content.html', true);  // Cambia la URL según el archivo con tu contenido
            xhr.onload = function() {
                if (xhr.status === 200) {
                    document.getElementById('contacto').innerHTML = xhr.responseText;
                }
            };
            xhr.send();
        }

        // Llamamos a la función para cargar el contenido al cargar la página
        window.onload = function() {
            loadContact();
        };
    </script>
</body>
</html>


