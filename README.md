<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dale Martinez | Developer Profile</title>
    <style>
        /* Importando uma fonte alternativa gótica/medieval para detalhes e Montserrat/Futura para o corpo */
        @import url('https://fonts.googleapis.com/css2?family=Cinzel:wght@700&family=Montserrat:wght@300;400;700&display=swap');

        :root {
            --bg-color: #050505;
            --card-bg: #0d0d0d;
            --primary-red: #8b0000;
            --neon-red: #ff1a1a;
            --text-color: #e0e0e0;
            --border-color: #260000;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-color);
            font-family: 'Futura', 'Century Gothic', 'Montserrat', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 40px 20px;
            overflow-x: hidden;
            background-image: 
                radial-gradient(circle at 10% 20%, rgba(139, 0, 0, 0.08) 0%, transparent 40%),
                radial-gradient(circle at 90% 80%, rgba(139, 0, 0, 0.08) 0%, transparent 40%);
        }

        /* Container Principal com animação de fade-in */
        .portfolio-container {
            width: 100%;
            max-width: 800px;
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 8px;
            padding: 30px;
            box-shadow: 0 0 30px rgba(0, 0, 0, 0.8), 0 0 15px rgba(139, 0, 0, 0.2);
            animation: fadeIn 1.2s ease-in-out;
            position: relative;
        }

        /* Linha decorativa gótica no topo */
        .portfolio-container::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 3px;
            background: linear-gradient(90deg, transparent, var(--neon-red), transparent);
            animation: pulseGlow 2s infinite alternate;
        }

        /* Cabeçalho / Identidade */
        .header {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            margin-bottom: 30px;
        }

        /* ASCII Art / Avatar Box */
        .avatar-box {
            font-family: monospace;
            font-size: 8px;
            line-height: 1.2;
            color: var(--neon-red);
            text-shadow: 0 0 8px rgba(255, 26, 26, 0.6);
            background: rgba(0, 0, 0, 0.6);
            padding: 15px;
            border-radius: 4px;
            border: 1px solid var(--border-color);
            margin-bottom: 20px;
            width: 100%;
            max-width: 320px;
            overflow-x: auto;
            white-space: pre;
            text-align: left;
            animation: glitch 1s infinite alternate;
        }

        h1 {
            font-family: 'Cinzel', 'Futura', serif;
            font-size: 2.5rem;
            color: #fff;
            text-shadow: 0 0 10px var(--neon-red);
            text-transform: uppercase;
            letter-spacing: 3px;
            margin-bottom: 5px;
        }

        .status-badge {
            display: inline-block;
            background: rgba(139, 0, 0, 0.2);
            border: 1px solid var(--neon-red);
            color: var(--neon-red);
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 2px;
            margin-top: 10px;
            box-shadow: 0 0 10px rgba(255, 26, 26, 0.3);
            animation: pulseBadge 1.5s infinite alternate;
        }

        /* Grid de Informações */
        .profile-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            margin-bottom: 30px;
        }

        @media (max-width: 600px) {
            .profile-grid {
                grid-template-columns: 1fr;
            }
        }

        /* Estilização das Tabelas (Gótico e Limpo) */
        .info-card {
            background: rgba(10, 10, 10, 0.8);
            border: 1px solid var(--border-color);
            border-radius: 4px;
            padding: 20px;
            transition: all 0.3s ease;
        }

        .info-card:hover {
            border-color: var(--neon-red);
            box-shadow: 0 0 15px rgba(255, 26, 26, 0.15);
            transform: translateY(-2px);
        }

        .info-card h3 {
            font-family: 'Cinzel', 'Futura', serif;
            color: var(--neon-red);
            border-bottom: 1px solid var(--primary-red);
            padding-bottom: 8px;
            margin-bottom: 15px;
            font-size: 1.2rem;
            letter-spacing: 1.5px;
            text-transform: uppercase;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            font-size: 0.95rem;
        }

        td {
            padding: 10px 8px;
            border-bottom: 1px solid rgba(139, 0, 0, 0.1);
        }

        tr:last-child td {
            border-bottom: none;
        }

        .label {
            color: #888;
            font-weight: bold;
            width: 40%;
        }

        .value {
            color: #fff;
            text-align: right;
        }

        /* Badge para Tecnologias */
        .tech-list {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }

        .tech-tag {
            background: rgba(20, 20, 20, 0.9);
            border: 1px solid rgba(139, 0, 0, 0.4);
            color: var(--text-color);
            padding: 6px 12px;
            border-radius: 3px;
            font-size: 0.85rem;
            transition: all 0.3s ease;
        }

        .tech-tag:hover {
            background: var(--primary-red);
            color: #fff;
            border-color: var(--neon-red);
            box-shadow: 0 0 8px var(--neon-red);
            cursor: default;
        }

        /* Animações */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes pulseGlow {
            0% { opacity: 0.5; }
            100% { opacity: 1; }
        }

        @keyframes pulseBadge {
            0% { box-shadow: 0 0 5px rgba(255, 26, 26, 0.2); }
            100% { box-shadow: 0 0 15px rgba(255, 26, 26, 0.6); }
        }

        @keyframes glitch {
            0% { text-shadow: 0 0 4px rgba(255, 26, 26, 0.4); }
            100% { text-shadow: 0 0 12px rgba(255, 26, 26, 0.8); }
        }
    </style>
</head>
<body>

    <div class="portfolio-container">
        
        <div class="header">
            <div class="avatar-box">
               .-+*####%%%=@@@*:%@#:              
              .:..:=:=#@%+%@@@+@@@@- ++            
                       .#@@@*@@@@%+@@@@+         
     ..:.                =@@@-%@@@@*@@@@@#@@%.-    
    .:: ...              %@@:   :.#@@@@@@@@@*@%:   
    ..-::-==..           @@#        .*@@%%@@%%@#.   
       =:-:-.:-....      @@          -  .+@@*@*-    
      :.-=**+.-:::-=---:==                .+#.    
        :-=++*:#*.:::-:-*==.              -#      
       :---:*=%=%#%**#-*-:.=-            -+.      
        -...:+*#**%%*=*%**#-:.          :* == -+*+-#*%####%*#=-         :          
           =*==+*#+###%#%%@@#*:.                  
             =@@%=:-*++**#%#+=##                  
               =*#@@@%:#@#+*+.+%%.                
                 #@@%%@@@@+-..=%%                
                   .*@@@@%@@#@@@=                
                       ::@%=%+* </div>
            <h1>Dale Martinez</h1>
            <p style="color: #888; letter-spacing: 1px;">@DaleMartinezDev</p>
            <div class="status-badge">ONLINE ● 100% Motivation</div>
        </div>

        <div class="profile-grid">
            
            <div class="info-card">
                <h3>System Info</h3>
                <table>
                    <tr>
                        <td class="label">Role</td>
                        <td class="value" style="color: var(--neon-red); font-weight: bold;">Developer</td>
                    </tr>
                    <tr>
                        <td class="label">Specialization</td>
                        <td class="value">Discord Bots, Backend, Automation</td>
                    </tr>
                    <tr>
                        <td class="label">Learning</td>
                        <td class="value">Cybersecurity</td>
                    </tr>
                    <tr>
                        <td class="label">Status</td>
                        <td class="value" style="color: #00ff66; text-shadow: 0 0 5px rgba(0, 255, 102, 0.4);">Unstoppable</td>
                    </tr>
                </table>
            </div>

            <div class="info-card">
                <h3>Terminal Stats</h3>
                <table>
                    <tr>
                        <td class="label">⭐ Stars</td>
                        <td class="value">42</td>
                    </tr>
                    <tr>
                        <td class="label">⚡ Commits</td>
                        <td class="value">1.2k</td>
                    </tr>
                    <tr>
                        <td class="label">📂 Repositories</td>
                        <td class="value">28</td>
                    </tr>
                    <tr>
                        <td class="label">👥 Followers</td>
                        <td class="value">35</td>
                    </tr>
                </table>
            </div>

        </div>

        <div class="info-card" style="margin-bottom: 0;">
            <h3>Weapon of Choice (Tech Stack)</h3>
            
            <div style="margin-bottom: 15px;">
                <p style="font-size: 0.8rem; text-transform: uppercase; color: #888; margin-bottom: 8px; letter-spacing: 1px;">Front-End</p>
                <div class="tech-list">
                    <span class="tech-tag">HTML</span>
                    <span class="tech-tag">CSS</span>
                    <span class="tech-tag">JavaScript</span>
                </div>
            </div>

            <div style="margin-bottom: 15px;">
                <p style="font-size: 0.8rem; text-transform: uppercase; color: #888; margin-bottom: 8px; letter-spacing: 1px;">Back-End</p>
                <div class="tech-list">
                    <span class="tech-tag">Node.js</span>
                    <span class="tech-tag">Python</span>
                </div>
            </div>

            <div style="margin-bottom: 15px;">
                <p style="font-size: 0.8rem; text-transform: uppercase; color: #888; margin-bottom: 8px; letter-spacing: 1px;">Database</p>
                <div class="tech-list">
                    <span class="tech-tag">MySQL</span>
                    <span class="tech-tag">SQLite</span>
                    <span class="tech-tag">MongoDB</span>
                </div>
            </div>

            <div>
                <p style="font-size: 0.8rem; text-transform: uppercase; color: #888; margin-bottom: 8px; letter-spacing: 1px;">Tools & OS</p>
                <div class="tech-list">
                    <span class="tech-tag">Git</span>
                    <span class="tech-tag">GitHub</span>
                    <span class="tech-tag">VS Code</span>
                    <span class="tech-tag">Linux</span>
                </div>
            </div>
        </div>

    </div>

</body>
</html>
