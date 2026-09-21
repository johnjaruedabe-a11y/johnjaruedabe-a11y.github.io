<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ciudadanía y Apropiación Digital</title>
    <style>
        :root {
            --color-fondo: #050505;
            --color-superficie: #0d0d0f;
            --color-tarjeta: #121214;
            --color-borde: #1e2621;
            --color-verde-principal: #10b981;
            --color-verde-claro: #34d399;
            --color-texto-principal: #f4f4f5;
            --color-texto-secundario: #a1a1aa;
        }
        * { box-sizing: border-box; }
        html { scroll-behavior: smooth; }
        body {
            margin: 0;
            padding: 0;
            background-color: var(--color-fondo);
            color: var(--color-texto-principal);
            font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
            line-height: 1.6;
        }
        .contenedor {
            width: 100%;
            max-width: 880px;
            margin: 0 auto;
            padding: 0 20px;
        }
        header#inicio {
            padding: 50px 0 35px 0;
            text-align: center;
            background: radial-gradient(ellipse 70% 50% at 50% 0%, rgba(16, 185, 129, 0.12), transparent);
            border-bottom: 1px solid #18201a;
        }
        header#inicio h1 {
            font-size: 2.25rem;
            font-weight: 800;
            color: #ffffff;
            margin: 0 0 10px 0;
        }
        header#inicio h1 span { color: var(--color-verde-principal); }
        .subtitulo {
            font-size: 1.05rem;
            color: var(--color-texto-secundario);
            margin: 0 0 25px 0;
        }
        .datos-estudiante {
            display: inline-flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 15px 30px;
            padding: 14px 24px;
            background-color: var(--color-superficie);
            border: 1px solid rgba(16, 185, 129, 0.3);
            border-radius: 12px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.6);
            text-align: left;
        }
        .datos-estudiante p { margin: 0; font-size: 0.88rem; color: #d4d4d8; }
        .datos-estudiante strong {
            color: var(--color-verde-claro);
            text-transform: uppercase;
            font-size: 0.75rem;
            letter-spacing: 0.05em;
            margin-right: 6px;
        }
        nav {
            position: sticky;
            top: 0;
            z-index: 50;
            background-color: rgba(5, 5, 5, 0.9);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid #1a221c;
        }
        nav ul {
            list-style: none;
            margin: 0;
            padding: 10px 0;
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 8px;
        }
        nav li a {
            display: block;
            padding: 8px 14px;
            color: #a1a1aa;
            text-decoration: none;
            font-size: 0.85rem;
            font-weight: 500;
            border-radius: 8px;
            transition: all 0.2s ease;
        }
        nav li a:hover {
            color: var(--color-verde-principal);
            background-color: rgba(16, 185, 129, 0.1);
        }
        main.contenedor { padding-top: 40px; padding-bottom: 60px; }
        .tarjeta {
            background-color: var(--color-tarjeta);
            border: 1px solid var(--color-borde);
            border-radius: 16px;
            padding: 28px;
            margin-bottom: 30px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.5);
            scroll-margin-top: 80px;
        }
        .tarjeta:hover { border-color: rgba(16, 185, 129, 0.35); }
        .tarjeta.bienvenida {
            background: linear-gradient(135deg, #0e120f 0%, #080808 100%);
            border-color: rgba(16, 185, 129, 0.3);
        }
        .tarjeta h2 {
            font-size: 1.45rem;
            font-weight: 700;
            color: #ffffff;
            margin: 0 0 6px 0;
        }
        .tarjeta h3 {
            font-size: 0.95rem;
            font-weight: 600;
            color: var(--color-verde-claro);
            margin: 0 0 22px 0;
            text-transform: uppercase;
            letter-spacing: 0.03em;
        }
        .concepto {
            background-color: #08080a;
            border: 1px solid #1c241e;
            border-radius: 12px;
            padding: 20px;
            margin-bottom: 16px;
        }
        .concepto h4 {
            font-size: 1.12rem;
            font-weight: 700;
            color: var(--color-verde-principal);
            margin: 0 0 8px 0;
        }
        .concepto p { margin: 0 0 10px 0; color: #d4d4d8; font-size: 0.95rem; }
        .ejemplo {
            background-color: #03140a;
            border-left: 3px solid var(--color-verde-principal);
            padding: 10px 14px;
            border-radius: 0 8px 8px 0;
            font-size: 0.88rem;
            color: #a7f3d0;
            margin-top: 10px;
        }
        .ejemplo strong { color: #34d399; margin-right: 4px; }
        .reflexion-caja {
            background: linear-gradient(180deg, #0f1612 0%, #09090b 100%);
            border: 1px solid rgba(16, 185, 129, 0.35);
            padding: 20px;
            border-radius: 12px;
            margin-top: 15px;
        }
        .reflexion-caja p {
            font-size: 1.02rem;
            line-height: 1.75;
            color: #e4e4e7;
            font-style: italic;
            padding-left: 10px;
            border-left: 2px solid var(--color-verde-principal);
            margin: 0;
        }
        footer {
            padding: 35px 20px;
            text-align: center;
            border-top: 1px solid #1a221c;
            background-color: #020202;
            color: #71717a;
            font-size: 0.85rem;
        }
        footer p { margin: 0; }
        @media (max-width: 640px) {
            header#inicio h1 { font-size: 1.75rem; }
            .datos-estudiante { flex-direction: column; gap: 8px; }
            nav ul { gap: 4px; }
            nav li a { padding: 6px 10px; font-size: 0.78rem; }
            .tarjeta { padding: 20px; }
        }
    </style>
</head>
<body>

    <header id="inicio">
        <div class="contenedor">
            <h1>Ciudadanía y <span>Apropiación Digital</span></h1>
            <p class="subtitulo">Uso práctico de herramientas digitales en actividades cotidianas.</p>
            
            <div class="datos-estudiante">
                <p><strong>Estudiante:</strong> John Jairo Rueda Bernal</p>
                <p><strong>Código:</strong> 127404</p>
            </div>
        </div>
    </header>

    <nav>
        <ul>
            <li><a href="#inicio">Inicio</a></li>
            <li><a href="#informacion">Información Digital</a></li>
            <li><a href="#economia">Economía Digital</a></li>
            <li><a href="#derechos">Derechos y Seguridad</a></li>
            <li><a href="#reflexion">Reflexión</a></li>
        </ul>
    </nav>

    <main class="contenedor">
        
        <div class="tarjeta bienvenida">
            <h2>Idea:</h2>
            <p>Explorar cómo las herramientas digitales transforman la vida diaria en comunicación, compras y protección de datos.</p>
            <div class="ejemplo">
                <strong>objetivo general:</strong> usar la tecnología para ser mejores ciudadanos en el mundo actual.
            </div>
        </div>

        <div class="tarjeta" id="informacion">
            <h2>Información Digital</h2>
            <h3>Problema a atacar: Garantizar buena comunicación y convivencia en la red</h3>

            <div class="concepto">
                <h4>Alfabetismo Digital</h4>
                <p>Desarrollar la capacidad de buscar entender y usar información inteligente en internet.</p>
                <div class="ejemplo">
                    <strong>Valor agregado:</strong> saber distinguir una noticia real de una falsa usando fuentes confiables
                </div>
            </div>

            <div class="concepto">
                <h4>Comunicación Digital</h4>
                <p>intercambio de ideas y mensajes a través de pantallas y las redes </p>
                <div class="ejemplo">
                    <strong>Valor agregado:</strong> participar de forma en videollamadas escolares o enviar tareas mediantes aulas virtuales
                </div>
            </div>

            <div class="concepto">
                <h4>Netiqueta</h4>
                <p>Aplicar reglas de educación y respeto al hablar con otros usuarios  en internet.</p>
                <div class="ejemplo">
                    <strong>Valor agregado:</strong> escribir con buena ortografía sin usar mayúsculas sostenidas para no gritar y brindar comentarios amables para los demas 
                </div>
            </div>
        </div>

        <div class="tarjeta" id="economia">
            <h2>Procesos Económicos Digitales</h2>
            <h3>Problema a atacar: Optimizar el intercambio comercial y el abastecimiento</h3>

            <div class="concepto">
                <h4>Economía Colaborativa</h4>
                <p>Uso de plataformas digitales para compartir alquilar o intercambiar bienes y servicios directamente.</p>
                <div class="ejemplo">
                    <strong>ejemplo:</strong> tecnología desarrolada en aplicaciones como Uber  DiDi o Airbnb para viajes y hospedaje.
                </div>
            </div>

            <div class="concepto">
                <h4>Comercio Electrónico / E-commerce</h4>
                <p>Compra y venta de productos o servicios utilizando  portales de internet.</p>
                <div class="ejemplo">
                    <strong>Valor agregado:</strong> el modelo permite comprar ropa o libros en Mercado Libre y Amazon además de pagar comida o pedir domicilios por Rappi ahorrando tiempo
                </div>
            </div>
        </div>

        <div class="tarjeta" id="derechos">
            <h2>Derechos Digitales y Seguridad en Línea</h2>
            <h3>Problema que se va a atacar: Reducir riesgos de hackeos acoso extoricion  y estafas en la web</h3>

            <div class="concepto">
                <h4>Protección de Datos</h4>
                <p>Garantizar que la información personal fotos y contraseñas estén seguras sin permisos ajenos</p>
                <div class="ejemplo">
                    <strong>Valor agregado:</strong> activar verificación en dos pasos en redes para evitar el robo de cuentas
                </div>
            </div>

            <div class="concepto">
                <h4>Derechos Digitales</h4>
                <p>Asegurar el derecho a acceder a internet y expresarse libremente en la red sin ser acosadas</p>
                <div class="ejemplo">
                    <strong>Valor agregado:</strong> denunciar y bloquear perfiles que hagan ciberbullying para mantener espacios seguros para toda la caomunidad 
                </div>
            </div>

            <div class="concepto">
                <h4>Deberes Ciudadanos y Seguridad</h4>
                <p>Cuidar lo que se hace en línea y respetar la privacidad de los demás.</p>
                <div class="ejemplo">
                    <strong>Contras a atacar:</strong> no compartir fotos o datos de amigos sin autorización y reportar cualquier  página sospechisa de que sea estafas
                </div>
            </div>
        </div>

        <div class="tarjeta" id="reflexion">
            <h2>Sección Final: Reflexión Personal</h2>
            <h3>Idea: Mi Vida en el Mundo Digital</h3>
            
            <div class="reflexion-caja">
                <p>Aplicar el alfabetismo digital para investigar tareas escolares y la Netiqueta para hablar con respeto en grupos de chat, proteger contraseñas y cuidar los datos de la comunidad entendiendo que internet es un espacio social y cultural enorme, el comercio electrónico permite ahorrar tiempo al comprar cosas directamente desde casa, el objetivo general es usar la tecnología para aportar cosas positivas, reduciendo riesgos y haciendo de internet un lugar más seguro y amigable para todos</p>
            </div>
        </div>
    </main>
</body>
</html>
