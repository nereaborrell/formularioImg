<?php
if ($_SERVER['REQUEST_METHOD'] === 'GET') {
    include 'captura.html';
    exit;
}

if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    // Sanitización
    $nombre = isset($_POST['nombre']) ? htmlspecialchars(trim($_POST['nombre']), ENT_QUOTES, 'UTF-8') : '';
    $alias  = isset($_POST['alias']) ? htmlspecialchars(trim($_POST['alias']), ENT_QUOTES, 'UTF-8') : '';
    $edad   = isset($_POST['edad']) ? intval($_POST['edad']) : '';
    
    $armas_array = isset($_POST['armas']) ? $_POST['armas'] : [];
    $armas_clean = array_map(function($a) {
        return htmlspecialchars($a, ENT_QUOTES, 'UTF-8');
    }, $armas_array);
    $armas = !empty($armas_clean) ? implode(', ', $armas_clean) : 'Ninguna';

    $magia = isset($_POST['magia']) ? htmlspecialchars($_POST['magia'], ENT_QUOTES, 'UTF-8') : 'No';

    // Subida de imagen
    $directorio_subida = 'uploads/';
    $ruta_imagen_guardada = '';
    $mensaje_error_imagen = '';
    $estado_imagen = 'ninguna';

    if (!file_exists($directorio_subida)) {
        @mkdir($directorio_subida, 0777, true);
    }

    if (isset($_FILES['imagen']) && $_FILES['imagen']['error'] !== UPLOAD_ERR_NO_FILE) {
        $file = $_FILES['imagen'];

        if ($file['error'] === UPLOAD_ERR_OK) {
            $extension = strtolower(pathinfo($file['name'], PATHINFO_EXTENSION));
            
            // Permitimos png, jpg, jpeg, gif
            $extensiones_permitidas = ['png', 'jpg', 'jpeg', 'gif'];

            if (!in_array($extension, $extensiones_permitidas)) {
                $estado_imagen = 'error';
                $mensaje_error_imagen = 'Error al subir la imagen: El formato debe ser imagen (PNG/JPG).';
            } else {
                $nombre_destino = 'img_' . time() . '_' . rand(100, 999) . '.' . $extension;
                $ruta_destino = $directorio_subida . $nombre_destino;

                if (move_uploaded_file($file['tmp_name'], $ruta_destino)) {
                    $estado_imagen = 'correcta';
                    $ruta_imagen_guardada = $ruta_destino;
                } else {
                    $estado_imagen = 'error';
                    $mensaje_error_imagen = 'Error al mover la imagen a la carpeta uploads.';
                }
            }
        } else {
            $estado_imagen = 'error';
            // Detalle técnico si PHP falla al recibir el archivo
            if ($file['error'] === UPLOAD_ERR_INI_SIZE || $file['error'] === UPLOAD_ERR_FORM_SIZE) {
                $mensaje_error_imagen = 'Error al subir la imagen: El archivo supera el peso máximo permitido por PHP.';
            } else {
                $mensaje_error_imagen = 'Error al subir la imagen (Código PHP: ' . $file['error'] . ')';
            }
        }
    } else {
        $estado_imagen = 'ninguna';
    }
?>
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Datos del Jugador</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #8B90A0;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
        }
        .card {
            background-color: #FFFF33;
            border-radius: 15px;
            padding: 30px;
            width: 500px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
            box-sizing: border-box;
        }
        .title {
            text-align: center;
            font-size: 22px;
            font-weight: bold;
            margin-bottom: 25px;
        }
        .content {
            display: flex;
            justify-content: space-between;
            gap: 20px;
        }
        .data-list { flex: 1; }
        .data-item { margin-bottom: 15px; line-height: 1.4; }
        .image-container {
            width: 180px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        .image-title { font-weight: bold; margin-bottom: 10px; text-align: center; }
        .img-box {
            border: 1px solid blue;
            width: 160px;
            height: 180px;
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: #FFFF33;
            overflow: hidden;
        }
        .img-box img {
            max-width: 100%;
            max-height: 100%;
            object-fit: contain;
        }
        .error-text {
            margin-top: 10px;
            font-size: 13px;
            text-align: center;
            color: #000;
        }
    </style>
</head>
<body>

<div class="card">
    <div class="title">Datos del Jugador</div>
    
    <div class="content">
        <div class="data-list">
            <div class="data-item"><strong>Nombre:</strong> <?php echo $nombre; ?></div>
            <div class="data-item"><strong>Alias:</strong> <?php echo $alias; ?></div>
            <div class="data-item"><strong>Edad:</strong> <?php echo $edad; ?></div>
            <div class="data-item"><strong>Armas seleccionadas:</strong> <?php echo $armas; ?></div>
            <div class="data-item"><strong>¿Practica artes mágicas?:</strong> <?php echo $magia; ?></div>
        </div>

        <div class="image-container">
            <?php if ($estado_imagen === 'correcta'): ?>
                <div class="image-title">Imagen subida:</div>
                <div class="img-box">
                    <img src="<?php echo $ruta_imagen_guardada; ?>" alt="Imagen Jugador">
                </div>

            <?php elseif ($estado_imagen === 'ninguna'): ?>
                <div class="image-title">No se subió ninguna imagen.</div>
                <div class="img-box">
                    <img src="calavera.png" alt="Calavera">
                </div>

            <?php elseif ($estado_imagen === 'error'): ?>
                <div class="image-title">No se subió ninguna imagen.</div>
                <div class="img-box">
                    <img src="calavera.png" alt="Calavera">
                </div>
                <div class="error-text"><?php echo $mensaje_error_imagen; ?></div>
            <?php endif; ?>
        </div>
    </div>
</div>

</body>
</html>
<?php } ?>
