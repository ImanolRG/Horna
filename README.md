# Horna
Fiestas 2025
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fiestas de Horna 2025</title>
    <style>
        /* Estilos generales */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .container {
            max-width: 400px; /* Tamaño optimizado para móviles */
            width: 95%;
            margin: 0 auto;
            background: white;
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
            overflow: hidden;
            min-height: 85vh; /* Ajuste para mejor visualización */
            display: flex;
            flex-direction: column;
        }

        /* Encabezado */
        header.header {
            background: linear-gradient(135deg, #ff6b6b, #ee5a24);
            color: white;
            padding: 20px;
            text-align: center;
            position: relative;
        }

        header.header h1 {
            font-size: 24px;
            margin-bottom: 5px;
        }

        header.header p {
            opacity: 0.9;
            font-size: 14px;
        }

        /* Navegación */
        nav.nav {
            display: flex;
            background: #f8f9fa;
            border-bottom: 1px solid #e9ecef;
        }

        .nav-item {
            flex: 1;
            padding: 15px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            border: none;
            background: none;
            font-size: 14px;
            color: #666;
            text-decoration: none; /* Asegura que no tenga subrayado si es un 'a' */
        }

        .nav-item.active {
            background: #667eea;
            color: white;
        }

        .nav-item:hover {
            background: #e9ecef;
        }

        .nav-item.active:hover {
            background: #5a6fd8;
        }

        /* Contenido de las secciones */
        .content {
            padding: 20px;
            flex-grow: 1; /* Permite que el contenido ocupe el espacio restante */
            overflow-y: auto; /* Permite el scroll si el contenido es largo */
        }

        section.section {
            display: none;
        }

        section.section.active {
            display: block;
            animation: fadeIn 0.3s ease-in;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Tarjetas de eventos */
        .event-card {
            background: #f8f9fa;
            border-radius: 15px;
            padding: 15px;
            margin-bottom: 15px;
            border-left: 4px solid #ff6b6b;
            transition: transform 0.2s ease, box-shadow 0.2s ease;
        }

        .event-card:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .event-time {
            font-weight: bold;
            color: #ff6b6b;
            font-size: 14px;
        }

        .event-title {
            font-size: 16px;
            margin: 5px 0;
            color: #333;
        }

        .event-location {
            color: #666;
            font-size: 14px;
        }

        .day-header {
            background: linear-gradient(135deg, #4ecdc4, #44a08d);
            color: white;
            padding: 15px;
            border-radius: 10px;
            margin-bottom: 20px;
            text-align: center;
            font-size: 18px;
            font-weight: bold;
        }

        /* Galería de fotos */
        .photo-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 10px;
            margin-bottom: 20px;
        }

        .photo-item {
            aspect-ratio: 1;
            background: #f0f0f0;
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #666;
            font-size: 12px;
            cursor: pointer;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
            border: 1px solid #e9ecef; /* Borde sutil */
        }

        .photo-item:hover {
            transform: scale(1.03); /* Menos exagerado para móviles */
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .photo-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block; /* Elimina espacio extra debajo de la imagen */
        }

        .photo-item-placeholder {
             width: 100%; 
             height: 100%; 
             display: flex; 
             align-items: center; 
             justify-content: center; 
             color: white; 
             font-size: 14px;
             text-align: center;
             padding: 10px;
             word-break: break-word; /* Rompe palabras largas */
        }

        .upload-btn {
            background: linear-gradient(135deg, #4ecdc4, #44a08d);
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: 25px;
            cursor: pointer;
            font-size: 14px;
            margin-bottom: 20px;
            width: 100%;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }

        .upload-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(78, 205, 196, 0.3);
        }

        /* Tarjetas de información */
        .info-card {
            background: #f8f9fa;
            border-radius: 15px;
            padding: 20px;
            margin-bottom: 15px;
            border-left: 4px solid #4ecdc4;
        }

        .info-title {
            font-size: 16px;
            font-weight: bold;
            color: #333;
            margin-bottom: 10px;
        }

        .info-text {
            color: #666;
            line-height: 1.5;
        }

        .contact-item {
            display: flex;
            align-items: center;
            padding: 10px 0;
            border-bottom: 1px solid #e9ecef;
        }

        .contact-item:last-child {
            border-bottom: none;
        }

        .contact-icon {
            width: 40px;
            height: 40px;
            background: #667eea;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 15px;
            color: white;
            font-size: 18px;
            flex-shrink: 0; /* Evita que el icono se encoja */
        }

        /* Modal de fotos */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.8);
            z-index: 1000;
            align-items: center;
            justify-content: center;
            animation: fadeInModal 0.2s ease-out;
        }

        .modal.active {
            display: flex;
        }

        @keyframes fadeInModal {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .modal-content {
            background: white;
            padding: 20px;
            border-radius: 15px;
            max-width: 90%; /* Ajuste para pantallas pequeñas */
            width: 400px; /* Ancho máximo para el modal */
            text-align: center;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
            animation: slideInModal 0.3s ease-out;
        }

        @keyframes slideInModal {
            from { transform: translateY(-50px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        .modal-image-wrapper {
            width: 100%;
            max-width: 350px; /* Tamaño máximo para la imagen dentro del modal */
            height: 250px; /* Altura fija para el contenedor de la imagen */
            background: #f0f0f0; /* Fondo si la imagen no carga */
            border-radius: 10px;
            margin: 0 auto 15px auto;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden; /* Asegura que la imagen no se salga del contenedor */
        }

        .modal-image-wrapper img {
            width: 100%;
            height: 100%;
            object-fit: contain; /* La imagen se ajusta sin recortarse */
            border-radius: 10px;
        }
        
        .modal-image-placeholder {
            color: #999;
            font-style: italic;
        }

        .close-btn {
            background: #ff6b6b;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 25px;
            cursor: pointer;
            margin-top: 10px;
            transition: background 0.2s ease;
        }

        .close-btn:hover {
            background: #e04a4a;
        }

        .download-btn {
            background: #4ecdc4;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 25px;
            cursor: pointer;
            margin: 10px 5px;
            transition: background 0.2s ease;
        }

        .download-btn:hover {
            background: #3cb0a5;
        }

        .hidden {
            display: none;
        }

        /* Mensaje de no hay fotos */
        #noPhotosMessage {
            text-align: center;
            color: #666;
            margin-top: 20px;
            font-style: italic;
        }

        /* Media queries para pantallas más grandes */
        @media (min-width: 600px) {
            .container {
                max-width: 600px; /* Mayor ancho en tablets */
                min-height: 70vh;
            }
            .photo-grid {
                grid-template-columns: repeat(3, 1fr); /* 3 columnas en pantallas más grandes */
            }
            .modal-content {
                max-width: 500px;
            }
            .modal-image-wrapper {
                max-width: 450px;
                height: 300px;
            }
        }
    </style>
</head>
<body>
    <main class="container">
        <header class="header">
            <h1>🎉 Fiestas de Horna 2025</h1>
            <p>Del 25 al 27 de Julio 2025</p>
        </header>

        <nav class="nav" role="tablist">
            <button class="nav-item active" role="tab" id="tab-horarios" aria-controls="horarios" aria-selected="true" data-section="horarios">📅 Horarios</button>
            <button class="nav-item" role="tab" id="tab-fotos" aria-controls="fotos" aria-selected="false" data-section="fotos">📸 Fotos</button>
            <button class="nav-item" role="tab" id="tab-info" aria-controls="info" aria-selected="false" data-section="info">ℹ️ Info</button>
        </nav>

        <div class="content">
            <section id="horarios" class="section active" role="tabpanel" aria-labelledby="tab-horarios">
                <h2 class="day-header">Viernes 25 de Julio</h2>
                <article class="event-card">
                    <div class="event-time">19:30</div>
                    <h3 class="event-title">Pregón y Chupinazo</h3>
                    <div class="event-location">Las Viejas Escuelas</div>
                </article>
                <article class="event-card">
                    <div class="event-time">20:00</div>
                    <h3 class="event-title">Mago Oliver & Liuba</h3>
                    <div class="event-location">Las Viejas Escuelas</div>
                </article>
                <article class="event-card">
                    <div class="event-time">21:00</div>
                    <h3 class="event-title">Pincho Pote (Morcilla)</h3>
                    <div class="event-location">Las Viejas Escuelas</div>
                </article>
                <article class="event-card">
                    <div class="event-time">21:30</div>
                    <h3 class="event-title">Bingo</h3>
                    <div class="event-location">Las Viejas Escuelas</div>
                </article>
                <article class="event-card">
                    <div class="event-time">22:00</div>
                    <h3 class="event-title">DJ Porty</h3>
                    <div class="event-location">Las Viejas Escuelas</div>
                </article>

                <h2 class="day-header">Sábado 26 de Julio</h2>
                <article class="event-card">
                    <div class="event-time">12:00</div>
                    <h3 class="event-title">Coral Miguel de Alonso</h3>
                    <div class="event-location">Las Viejas Escuelas</div>
                </article>
                <article class="event-card">
                    <div class="event-time">12:00 - 14:30</div>
                    <h3 class="event-title">Hinchables</h3>
                    <div class="event-location">Las Viejas Escuelas</div>
                </article>
                <article class="event-card">
                    <div class="event-time">13:00</div>
                    <h3 class="event-title">Torneo de Tuta</h3>
                    <div class="event-location">Las Viejas Escuelas</div>
                </article>
                <article class="event-card">
                    <div class="event-time">14:30</div>
                    <h3 class="event-title">Paella Popular + Postre 3€</h3>
                    <div class="event-location">Las Viejas Escuelas</div>
                </article>
                <article class="event-card">
                    <div class="event-time">16:00</div>
                    <h3 class="event-title">Torneo Mus y Brisca</h3>
                    <div class="event-location">Las Viejas Escuelas</div>
                </article>
                <article class="event-card">
                    <div class="event-time">17:00</div>
                    <h3 class="event-title">Fiesta de la Espuma</h3>
                    <div class="event-location">Las Viejas Escuelas</div>
                </article>
                <article class="event-card">
                    <div class="event-time">17:00</div>
                    <h3 class="event-title">Ginkana Infantil / Wipeout</h3>
                    <div class="event-location">Las Viejas Escuelas</div>
                </article>
                <article class="event-card">
                    <div class="event-time">19:30</div>
                    <h3 class="event-title">Juegos en Grupo - Adultos</h3>
                    <div class="event-location">Las Viejas Escuelas</div>
                </article>
                <article class="event-card">
                    <div class="event-time">21:00</div>
                    <h3 class="event-title">Bingo</h3>
                    <div class="event-location">Las Viejas Escuelas</div>
                </article>
                <article class="event-card">
                    <div class="event-time">21:30</div>
                    <h3 class="event-title">Pinchos Morunos 2€</h3>
                    <div class="event-location">Las Viejas Escuelas</div>
                </article>
                <article class="event-card">
                    <div class="event-time">21:30</div>
                    <h3 class="event-title">Verbena "Orquesta Agua"</h3>
                    <div class="event-location">Las Viejas Escuelas</div>
                </article>
                <article class="event-card">
                    <div class="event-time">00:00</div>
                    <h3 class="event-title">Concurso de Baile</h3>
                    <div class="event-location">Las Viejas Escuelas</div>
                </article>

                <h2 class="day-header">Domingo 27 de Julio</h2>
                <article class="event-card">
                    <div class="event-time">12:00</div>
                    <h3 class="event-title">Misa con Coro</h3>
                    <div class="event-location">Iglesia Parroquial</div>
                </article>
                <article class="event-card">
                    <div class="event-time">13:00</div>
                    <h3 class="event-title">Juegos Populares en Familia</h3>
                    <div class="event-location">Las Viejas Escuelas</div>
                </article>
                <article class="event-card">
                    <div class="event-time">13:30</div>
                    <h3 class="event-title">Vermut Chistorra a la Sidra</h3>
                    <div class="event-location">Las Viejas Escuelas</div>
                </article>
                <article class="event-card">
                    <div class="event-time">15:00</div>
                    <h3 class="event-title">A Comer Donde Se Pueda</h3>
                    <div class="event-location">Libre</div>
                </article>
                <article class="event-card">
                    <div class="event-time">16:30</div>
                    <h3 class="event-title">Torneo de Tute</h3>
                    <div class="event-location">Las Viejas Escuelas</div>
                </article>
                <article class="event-card">
                    <div class="event-time">18:00</div>
                    <h3 class="event-title">Entrega de Premios</h3>
                    <div class="event-location">Las Viejas Escuelas</div>
                </article>
                <article class="event-card">
                    <div class="event-time">18:00</div>
                    <h3 class="event-title">Sorteo de Jamón - BINGOOOOOOOOO</h3>
                    <div class="event-location">Las Viejas Escuelas</div>
                </article>
            </section>

            <section id="fotos" class="section" role="tabpanel" aria-labelledby="tab-fotos" hidden>
                <button class="upload-btn" aria-label="Subir foto" onclick="document.getElementById('fileInput').click()">
                    📷 Subir Foto
                </button>
                <input type="file" id="fileInput" accept="image/*" class="hidden" onchange="handleFileSelect(event)">
                
                <div class="photo-grid" id="photoGrid">
                    <div class="photo-item" onclick="viewPhoto('https://via.placeholder.com/150/ff6b6b/ffffff?text=Pregón+2024', 'Pregón 2024')">
                        <img src="https://via.placeholder.com/150/ff6b6b/ffffff?text=Pregón+2024" alt="Foto del Pregón 2024">
                    </div>
                    <div class="photo-item" onclick="viewPhoto('https://via.placeholder.com/150/4ecdc4/ffffff?text=Verbena', 'Verbena')">
                        <img src="https://via.placeholder.com/150/4ecdc4/ffffff?text=Verbena" alt="Foto de la Verbena">
                    </div>
                    <div class="photo-item" onclick="viewPhoto('https://via.placeholder.com/150/667eea/ffffff?text=Procesión', 'Procesión')">
                        <img src="https://via.placeholder.com/150/667eea/ffffff?text=Procesión" alt="Foto de la Procesión">
                    </div>
                    <div class="photo-item" onclick="viewPhoto('https://via.placeholder.com/150/feca57/ffffff?text=Fuegos', 'Fuegos artificiales')">
                        <img src="https://via.placeholder.com/150/feca57/ffffff?text=Fuegos" alt="Foto de los Fuegos Artificiales">
                    </div>
                </div>
                <p id="noPhotosMessage" class="hidden">¡Sé el primero en subir una foto!</p>
            </section>

            <section id="info" class="section" role="tabpanel" aria-labelledby="tab-info" hidden>
                <article class="info-card">
                    <h2 class="info-title">📍 Sobre Horna</h2>
                    <p class="info-text">
                        Horna es un hermoso pueblo que celebra sus fiestas patronales cada año en agosto. 
                        Nuestras tradiciones se remontan a siglos atrás y son el corazón de nuestra comunidad.
                    </p>
                </article>

                <article class="info-card">
                    <h2 class="info-title">🎯 Contactos Importantes</h2>
                    <div class="contact-item">
                        <div class="contact-icon" aria-hidden="true">🏛️</div>
                        <div>
                            <strong>Ayuntamiento</strong><br>
                            <a href="tel:+34987123456" style="color: #666; text-decoration: none;">987 123 456</a>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon" aria-hidden="true">🚑</div>
                        <div>
                            <strong>Emergencias</strong><br>
                            <a href="tel:+34112" style="color: #666; text-decoration: none;">112</a>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon" aria-hidden="true">🎉</div>
                        <div>
                            <strong>Comisión de Fiestas</strong><br>
                            <a href="tel:+34987654321" style="color: #666; text-decoration: none;">987 654 321</a>
                        </div>
                    </div>
                </article>

                <article class="info-card">
                    <h2 class="info-title">⚠️ Avisos Importantes</h2>
                    <ul class="info-text" style="list-style-type: disc; margin-left: 20px;">
                        <li>Fecha límite de inscripción paella popular: hasta el 23 de julio</li>
                        <li>Inscripciones en el local de la Asociación la Amistad (antiguas escuelas)</li>
                        <li>Programa sujeto a posibles cambios</li>
                        <li>La comisión de fiestas no se hace responsable de daños personales y materiales</li>
                    </ul>
                </article>

                <article class="info-card">
                    <h2 class="info-title">🤝 Colaboradores</h2>
                    <p class="info-text">
                        Admon. Loterías Las Merindades, Animalvet, Bar el Soto, Callejo, Carnicería Ana, Carpin, Carrocerías Japi, Comercial de Gasolinera de Oña, Comercial Palencia, Díez Pariente, Fenorte, Foncal, Const. Fortunato, Gescor, Comercial Los Leones, Mara, Mozares, Calzados Madían, Salinera (La Noria), Frutería Santoñes, Seragi, Vía Verde.
                    </p>
                </article>
            </section>
        </div>
    </main>

    <div id="photoModal" class="modal" role="dialog" aria-modal="true" aria-labelledby="modalTitle" tabindex="-1">
        <div class="modal-content">
            <h2 id="modalTitle" class="hidden">Vista de Foto</h2>
            <div id="modalImage" class="modal-image-wrapper">
                <p class="modal-image-placeholder">Cargando imagen...</p>
            </div>
            <button class="download-btn" onclick="downloadPhoto()">⬇️ Descargar</button>
            <button class="close-btn" onclick="closeModal()">Cerrar</button>
        </div>
    </div>

    <script>
        let photos = [
            // Puedes precargar algunas fotos aquí si lo deseas
            // { id: 1, src: 'path/to/my_preloaded_image.jpg', name: 'Mi foto precargada', date: '14/07/2025' }
        ];
        let currentPhoto = null; // Almacena el objeto de la foto actual para la descarga

        document.addEventListener('DOMContentLoaded', () => {
            // Inicializar la primera sección activa y su botón de navegación
            const initialSectionId = 'horarios';
            document.getElementById(initialSectionId).classList.add('active');
            document.getElementById(`tab-${initialSectionId}`).classList.add('active');
            document.getElementById(`tab-${initialSectionId}`).setAttribute('aria-selected', 'true');
            document.getElementById(initialSectionId).removeAttribute('hidden');

            // Manejadores de eventos para los botones de navegación
            document.querySelectorAll('.nav-item').forEach(button => {
                button.addEventListener('click', (event) => {
                    const targetButton = event.currentTarget; // Usa currentTarget para el botón
                    const sectionId = targetButton.dataset.section;

                    // Desactivar todas las secciones y botones
                    document.querySelectorAll('.section').forEach(section => {
                        section.classList.remove('active');
                        section.setAttribute('hidden', ''); // Ocultar con hidden para accesibilidad
                    });
                    document.querySelectorAll('.nav-item').forEach(item => {
                        item.classList.remove('active');
                        item.setAttribute('aria-selected', 'false');
                    });

                    // Activar la sección y botón seleccionados
                    document.getElementById(sectionId).classList.add('active');
                    document.getElementById(sectionId).removeAttribute('hidden');
                    targetButton.classList.add('active');
                    targetButton.setAttribute('aria-selected', 'true');

                    // Lógica específica para la sección de fotos
                    if (sectionId === 'fotos') {
                        updatePhotoGrid(); // Actualiza la visibilidad del mensaje "no hay fotos"
                    }
                });
            });

            // Cerrar modal al hacer clic fuera
            document.getElementById('photoModal').addEventListener('click', function(e) {
                if (e.target === this) {
                    closeModal();
                }
            });

            // Actualizar el grid de fotos al cargar por si hay precargadas
            updatePhotoGrid();
        });

        // Función para añadir una foto al grid
        function addPhotoToGrid(photo) {
            const photoGrid = document.getElementById('photoGrid');
            const photoItem = document.createElement('div');
            photoItem.className = 'photo-item';
            photoItem.setAttribute('role', 'img'); // Indica que es una imagen o un contenedor de imagen
            photoItem.setAttribute('aria-label', photo.name); // Proporciona un label accesible

            // Usa un listener de eventos para la imagen
            photoItem.addEventListener('click', () => viewPhoto(photo.src, photo.name, photo.id));
            
            const img = document.createElement('img');
            img.src = photo.src;
            img.alt = photo.name; // Alt text descriptivo
            
            photoItem.appendChild(img);
            photoGrid.appendChild(photoItem);
            updatePhotoGrid(); // Recalcula si mostrar el mensaje de "no hay fotos"
        }

        // Manejar la selección de archivos
        function handleFileSelect(event) {
            const file = event.target.files[0];
            if (file && file.type.startsWith('image/')) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    const photoData = {
                        id: Date.now(), // ID único
                        src: e.target.result,
                        name: file.name,
                        date: new Date().toLocaleDateString('es-ES') // Formato de fecha español
                    };
                    photos.push(photoData);
                    addPhotoToGrid(photoData);
                };
                reader.readAsDataURL(file);
            } else {
                alert('Por favor, selecciona un archivo de imagen válido.');
            }
            // Limpiar el input para permitir subir el mismo archivo de nuevo si es necesario
            event.target.value = ''; 
        }

        // Ver una foto en el modal
        function viewPhoto(src, altText, photoId = null) {
            const modal = document.getElementById('photoModal');
            const modalImageWrapper = document.getElementById('modalImage');
            
            modalImageWrapper.innerHTML = ''; // Limpiar contenido previo

            const img = document.createElement('img');
            img.src = src;
            img.alt = altText;
            
            modalImageWrapper.appendChild(img);
            currentPhoto = photoId ? photos.find(p => p.id === photoId) : null; // Guardar la foto si es real

            // Mostrar u ocultar el botón de descarga para las fotos de muestra
            const downloadBtn = document.querySelector('#photoModal .download-btn');
            if (currentPhoto) {
                downloadBtn.style.display = 'inline-block';
            } else {
                downloadBtn.style.display = 'none'; // Ocultar para fotos de muestra
            }

            modal.classList.add('active');
            modal.focus(); // Enfocar el modal para accesibilidad
        }

        // Cerrar el modal
        function closeModal() {
            document.getElementById('photoModal').classList.remove('active');
            currentPhoto = null; // Limpiar la foto actual
        }

        // Descargar la foto actual
        function downloadPhoto() {
            if (currentPhoto) {
                const link = document.createElement('a');
                link.download = currentPhoto.name;
                link.href = currentPhoto.src;
                document.body.appendChild(link); // Necesario para Firefox
                link.click();
                document.body.removeChild(link); // Limpiar
            } else {
                alert('Esta es una foto de muestra. Sube tus propias fotos para poder descargarlas.');
            }
        }

        // Actualiza el mensaje de "no hay fotos"
        function updatePhotoGrid() {
            const photoGrid = document.getElementById('photoGrid');
            const noPhotosMessage = document.getElementById('noPhotosMessage');
            
            // Contar solo las fotos subidas por el usuario, no los ejemplos iniciales
            const userUploadedPhotosCount = photos.length; 
            const initialSamplePhotosCount = 4; // Contar las fotos de ejemplo precargadas en el HTML

            // Si solo hay las fotos de ejemplo y no se han subido más, mostrar el mensaje
            if (userUploadedPhotosCount === 0 && photoGrid.children.length === initialSamplePhotosCount) {
                 noPhotosMessage.classList.add('hidden'); // Ocultar si hay ejemplos
            } else if (userUploadedPhotosCount > 0) {
                 noPhotosMessage.classList.add('hidden'); // Ocultar si ya hay fotos de usuario
            } else {
                noPhotosMessage.classList.remove('hidden'); // Mostrar si no hay fotos de usuario y los ejemplos se quitaran
            }
        }
        // Llamar para asegurar que el mensaje se oculta si ya hay fotos
        updatePhotoGrid();

    </script>
</body>
</html>
