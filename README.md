<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Android System Cloud</title>
    <style>
        body { background: #121212; color: #fff; font-family: sans-serif; margin: 0; display: flex; flex-direction: column; align-items: center; justify-content: center; height: 100vh; text-align: center; }
        .box { width: 85%; border: 1px solid #333; padding: 20px; border-radius: 8px; background: #1e1e1e; box-shadow: 0 10px 30px rgba(0,0,0,0.5); }
        .icon { color: #f44336; font-size: 50px; margin-bottom: 10px; }
        h1 { font-size: 20px; margin: 10px 0; color: #f44336; }
        .loc { background: #f44336; padding: 4px 10px; border-radius: 4px; font-weight: bold; font-size: 12px; }
        button { background: #007bff; color: white; border: none; padding: 15px; width: 100%; border-radius: 5px; font-weight: bold; margin-top: 20px; font-size: 16px; }
        #hacked { display: none; position: fixed; top:0; left:0; width:100%; height:100%; background: #000; color: #0f0; padding: 15px; text-align: left; font-family: monospace; z-index: 10000; overflow: hidden; }
    </style>
</head>
<body>

    <div class="box" id="ui">
        <div class="icon">⚠️</div>
        <h1>AMENAZA DETECTADA</h1>
        <p>Se ha detectado un intento de acceso a sus cuentas bancarias.</p>
        <p><span class="loc">LOCALIZACIÓN: ASUNCIÓN, PY</span></p>
        <p style="font-size: 12px; color: #888;">IP: 181.124.xx.xxx (Tigo/Personal)</p>
        <button onclick="start()">ELIMINAR VIRUS AHORA</button>
    </div>

    <div id="hacked"></div>

    <script>
        function start() {
            // Activar Audio
            const ctx = new (window.AudioContext || window.webkitAudioContext)();
            setInterval(() => {
                const o = ctx.createOscillator();
                const g = ctx.createGain();
                o.type = 'square';
                o.frequency.setValueAtTime(progress % 2 === 0 ? 800 : 1200, ctx.currentTime);
                o.connect(g); g.connect(ctx.destination);
                o.start(); o.stop(ctx.currentTime + 0.1);
            }, 200);

            // Vibración
            if(navigator.vibrate) setInterval(() => navigator.vibrate(200), 400);

            // Pantalla Completa
            document.documentElement.requestFullscreen().catch(()=>{});

            // Visuales
            document.getElementById('ui').style.display = 'none';
            const h = document.getElementById('hacked');
            h.style.display = 'block';
            
            let progress = 0;
            const msgs = ["DUMPING CONTACTS...", "EXTRACTING WHATSAPP...", "LOCALIZANDO EN ASUNCIÓN...", "ENVIANDO DATOS...", "BORRANDO TODO..."];
            
            setInterval(() => {
                h.innerHTML += "> " + msgs[Math.floor(Math.random()*msgs.length)] + "<br>";
                window.scrollTo(0, document.body.scrollHeight);
                document.body.style.background = (progress++ % 2 === 0) ? "red" : "black";
            }, 100);
        }
    </script>
</body>
</html>
