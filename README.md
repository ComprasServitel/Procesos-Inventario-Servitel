<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Control Operativo de Inventarios - Servitel</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        /* Identidad Visual Servitel */
        :root {
            --azul-servitel: #0873a7;
            --verde-servitel: #41d148;
        }

        body {
            font-family: 'Calibri', 'Segoe UI', Tahoma, sans-serif;
            background: #f8fafc;
            color: #1e293b;
            margin: 0;
            padding: 0;
        }

        .header-gradient {
            background: linear-gradient(90deg, var(--azul-servitel) 0%, #065a82 100%);
        }

        /* CONFIGURACIÓN DE IMPRESIÓN REQUERIDA (Márgenes Eduard Guedez) */
        @page {
            size: A4;
            /* Superior 3cm, Derecho 3cm, Inferior 3cm, Izquierdo 2.5cm */
            margin: 3cm 3cm 3cm 2.5cm;
        }

        @media print {
            .no-print { display: none !important; }
            body { background: white !important; padding: 0 !important; }
            .main-container {
                box-shadow: none !important;
                border: none !important;
                width: 100% !important;
                max-width: none !important;
                margin: 0 !important;
            }
            .content-area { padding: 0 !important; }
        }

        /* Estilos de Texto según Manual de Estilo */
        .titulo-26 {
            font-size: 26pt;
            line-height: 1.0;
            text-align: center;
            font-weight: 900;
            text-transform: uppercase;
        }

        .subtitulo-14 {
            font-size: 14pt;
            line-height: 1.15;
            font-weight: bold;
            text-transform: uppercase;
            border-bottom: 2px solid var(--azul-servitel);
            padding-bottom: 4px;
            margin-bottom: 1rem;
        }

        .cuerpo-11 {
            font-size: 11pt;
            line-height: 1.15;
            text-align: justify;
        }

        .card-proceso {
            border-left: 5px solid var(--azul-servitel);
            background: #f1f5f9;
            padding: 15px;
            border-radius: 0 8px 8px 0;
        }

        .card-proceso-verde {
            border-left: 5px solid var(--verde-servitel);
            background: #f0fdf4;
            padding: 15px;
            border-radius: 0 8px 8px 0;
        }
    </style>
</head>
<body class="p-4 md:p-10">

    <div class="max-w-4xl mx-auto main-container bg-white shadow-2xl rounded-xl overflow-hidden border border-slate-200">
        
        <!-- Encabezado Institucional -->
        <div class="header-gradient p-10 text-white">
            <div class="flex flex-col items-center gap-4">
                <div class="bg-white p-3 rounded-xl shadow-lg">
                    <svg width="45" height="45" viewBox="0 0 24 24" fill="none" stroke="#0873a7" stroke-width="2">
                        <path d="M21 8a2 2 0 0 0-1-1.73l-7-4a2 2 0 0 0-2 0l-7 4A2 2 0 0 0 3 8v8a2 2 0 0 0 1 1.73l7 4a2 2 0 0 0 2 0l7-4A2 2 0 0 0 21 16Z"/>
                        <path d="m3.3 7 8.7 5 8.7-5M12 22V12"/>
                        <circle cx="18.5" cy="15.5" r="3" fill="#41d148" stroke="#41d148"/>
                        <path d="m17.5 15.5 0.7 0.7 1.5-1.5" stroke="white" stroke-width="1.2"/>
                    </svg>
                </div>
                <h1 class="titulo-26">Control Operativo de Inventarios</h1>
                <div class="mt-2 bg-white/20 px-6 py-1 rounded-full border border-white/30">
                    <p class="text-[10pt] font-bold uppercase tracking-widest">Servitel - Gerencia de Compras e Inventario</p>
                </div>
            </div>
        </div>

        <!-- Cuerpo del Documento -->
        <div class="content-area p-10 cuerpo-11">
            
            <div class="grid grid-cols-1 md:grid-cols-2 gap-10 mb-10">
                <!-- Columna Instalación -->
                <div class="space-y-4">
                    <h2 class="subtitulo-14 text-slate-800">Eje de Instalación</h2>
                    <div class="card-proceso">
                        <h3 class="font-bold text-[#0873a7]">Almacén de Materiales Principal</h3>
                        <p class="text-slate-600 mt-1">Recepción masiva y tránsito hacia operaciones.</p>
                    </div>
                    <div class="flex justify-center py-2">
                        <svg width="20" height="20" fill="none" stroke="#0873a7" stroke-width="3" viewBox="0 0 24 24"><path d="m7 10 5 5 5-5M12 15V3"/></svg>
                    </div>
                    <div class="card-proceso-verde">
                        <h3 class="font-bold text-emerald-800 uppercase text-[10pt]">Almacén Técnico Instalador</h3>
                        <p class="text-slate-600">Material exclusivo para nuevas altas.</p>
                    </div>
                </div>

                <!-- Columna Soporte -->
                <div class="space-y-4">
                    <h2 class="subtitulo-14 text-slate-800">Eje de Soporte</h2>
                    <div class="card-proceso">
                        <h3 class="font-bold text-[#0873a7]">Almacén para Reparación</h3>
                        <p class="text-slate-600 mt-1">Inventario para contingencias y mantenimiento.</p>
                    </div>
                    <div class="flex justify-center py-2">
                        <svg width="20" height="20" fill="none" stroke="#0873a7" stroke-width="3" viewBox="0 0 24 24"><path d="m7 10 5 5 5-5M12 15V3"/></svg>
                    </div>
                    <div class="card-proceso-verde">
                        <h3 class="font-bold text-emerald-800 uppercase text-[10pt]">Almacén Técnico Soporte</h3>
                        <p class="text-slate-600">Material exclusivo para reparaciones.</p>
                    </div>
                </div>
            </div>

            <!-- Restricciones Operativas -->
            <div class="bg-slate-50 border border-slate-200 rounded-xl p-6 mb-10">
                <h2 class="subtitulo-14 text-slate-800 mb-4">Restricciones de Almacén</h2>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                    <div class="bg-white p-4 rounded border-t-4 border-[#0873a7] shadow-sm">
                        <h4 class="font-black text-[9pt] uppercase mb-1">Bodega de Ventas</h4>
                        <p class="text-slate-500 italic text-[10pt]">Solo para comercialización. No transferible a técnicos.</p>
                    </div>
                    <div class="bg-white p-4 rounded border-t-4 border-[#41d148] shadow-sm">
                        <h4 class="font-black text-[9pt] uppercase mb-1">Bodega de Construcción</h4>
                        <p class="text-slate-500 italic text-[10pt]">Gestión de infraestructura y red matriz.</p>
                    </div>
                </div>
            </div>

            <!-- Nota de Seguridad -->
            <div class="bg-red-700 p-8 rounded-xl text-white text-center shadow-lg">
                <h5 class="text-[13pt] font-black uppercase mb-2">Protocolo de Seguridad Inviolable</h5>
                <p class="font-bold uppercase leading-tight text-[10pt]">
                    Prohibida la salida de material sin registro sistémico previo y firma de acta de entrega por el responsable.
                </p>
            </div>
        </div>

        <!-- Botón de Emergencia (Solo visible en pantalla) -->
        <div class="no-print bg-slate-100 p-8 border-t border-slate-200 text-center">
            <p class="text-slate-500 mb-4 text-sm font-bold">
                ESTE DOCUMENTO ESTÁ CONFIGURADO CON MÁRGENES DE 3CM Y 2.5CM.
            </p>
            <button onclick="window.print()" class="bg-[#0873a7] hover:bg-sky-800 text-white px-12 py-4 rounded-xl font-black text-sm shadow-xl flex items-center gap-3 mx-auto uppercase tracking-tighter">
                <svg width="20" height="20" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24"><path d="M6 9V2h12v7M6 18H4a2 2 0 0 1-2-2v-5a2 2 0 0 1 2-2h16a2 2 0 0 1 2 2v5a2 2 0 0 1-2 2h-2M6 14h12v8H6z"/></svg>
                Generar PDF Ahora
            </button>
            <p class="mt-4 text-xs text-slate-400 uppercase">Si el botón no responde, usa Ctrl + P</p>
        </div>
    </div>

    <script>
        // Intento de auto-ejecución al cargar si el entorno lo permite
        window.onload = function() {
            console.log("Documento listo para impresión corporativa Servitel");
        };
    </script>
</body>
</html>
