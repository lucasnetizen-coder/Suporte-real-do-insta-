<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simulação Educacional de Phishing</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 20px;
            color: #333;
        }
        
        .container {
            width: 100%;
            max-width: 800px;
            background: white;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            overflow: hidden;
            margin: 20px 0;
        }
        
        header {
            background: #405DE6;
            color: white;
            text-align: center;
            padding: 20px;
        }
        
        .warning {
            background: #FFEAA7;
            color: #D63031;
            padding: 15px;
            text-align: center;
            font-weight: bold;
            border-left: 5px solid #D63031;
        }
        
        .content {
            padding: 30px;
        }
        
        .login-form {
            background: #F8F9FA;
            padding: 25px;
            border-radius: 10px;
            margin: 20px 0;
            border: 1px solid #E9ECEF;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
        }
        
        input[type="text"],
        input[type="password"] {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #CED4DA;
            border-radius: 8px;
            font-size: 16px;
            transition: border-color 0.3s;
        }
        
        input[type="text"]:focus,
        input[type="password"]:focus {
            border-color: #405DE6;
            outline: none;
        }
        
        button {
            background: #405DE6;
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: 8px;
            cursor: pointer;
            font-size: 16px;
            font-weight: 600;
            width: 100%;
            transition: background 0.3s;
        }
        
        button:hover {
            background: #3A4ED5;
        }
        
        .result {
            display: none;
            background: #F1F3F5;
            padding: 20px;
            border-radius: 10px;
            margin-top: 20px;
            text-align: center;
        }
        
        .educational-content {
            margin-top: 30px;
            padding: 20px;
            background: #E3F2FD;
            border-radius: 10px;
        }
        
        h1, h2, h3 {
            margin-bottom: 15px;
            color: #343A40;
        }
        
        p {
            margin-bottom: 15px;
            line-height: 1.6;
        }
        
        ul {
            margin-left: 20px;
            margin-bottom: 15px;
        }
        
        li {
            margin-bottom: 8px;
        }
        
        footer {
            text-align: center;
            margin-top: 20px;
            color: white;
            font-size: 14px;
        }
        
        .logo {
            font-size: 24px;
            font-weight: bold;
            margin-bottom: 10px;
            color: #405DE6;
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>Simulação Educacional de Phishing</h1>
            <p>Esta é uma demonstração para fins educacionais</p>
        </header>
        
        <div class="warning">
            ⚠️ AVISO: Esta é apenas uma simulação educacional. Não tente usar essas técnicas para atividades maliciosas.
        </div>
        
        <div class="content">
            <h2>Como funciona o phishing?</h2>
            <p>Phishing é uma técnica onde criminosos criam páginas falsas que se passam por serviços legítimos para roubar credenciais de login.</p>
            
            <div class="login-form">
                <div class="logo">instagram</div>
                <h3>Faça login na sua conta</h3>
                <div class="form-group">
                    <label for="username">Nome de usuário ou email</label>
                    <input type="text" id="username" placeholder="Seu nome de usuário">
                </div>
                <div class="form-group">
                    <label for="password">Senha</label>
                    <input type="password" id="password" placeholder="Sua senha">
                </div>
                <button onclick="simulatePhishing()">Entrar</button>
            </div>
            
            <div id="result" class="result">
                <h3>⚠️ Simulação Bem-Sucedida</h3>
                <p>Em um ataque real, suas credenciais teriam sido roubadas!</p>
                <p><strong>Nome de usuário:</strong> <span id="capturedUsername"></span></p>
                <p><strong>Senha:</strong> <span id="capturedPassword"></span></p>
            </div>
            
            <div class="educational-content">
                <h2>Como se proteger do phishing?</h2>
                <ul>
                    <li>Verifique sempre o URL do site - deve ser "https://www.instagram.com"</li>
                    <li>Nunca clique em links suspeitos de e-mails ou mensagens</li>
                    <li>Habilite a autenticação de dois fatores (2FA)</li>
                    <li>Use senhas fortes e únicas para cada serviço</li>
                    <li>Desconfie de mensagens urgentes ou promessas boas demais</li>
                </ul>
                
                <h3>O que fazer se cair em um phishing?</h3>
                <ul>
                    <li>Altere imediatamente sua senha</li>
                    <li>Verifique se há atividades suspeitas em sua conta</li>
                    <li>Habilite a autenticação de dois fatores</li>
                    <li>Entre em contato com o suporte oficial do serviço</li>
                </ul>
            </div>
        </div>
    </div>
    
    <footer>
        <p>Esta simulação foi criada apenas para fins educacionais e de conscientização.</p>
        <p>© 2023 - Simulação de Segurança Digital</p>
    </footer>

    <script>
        function simulatePhishing() {
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;
            
            if (!username || !password) {
                alert('Por favor, preencha ambos os campos para a simulação.');
                return;
            }
            
            // Mostrar os dados capturados (apenas para demonstração)
            document.getElementById('capturedUsername').textContent = username;
            document.getElementById('capturedPassword').textContent = password;
            
            // Mostrar o resultado
            document.getElementById('result').style.display = 'block';
            
            // Rolar para o resultado
            document.getElementById('result').scrollIntoView({ behavior: 'smooth' });
            
            // Limpar os campos (apenas para demonstração)
            document.getElementById('username').value = '';
            document.getElementById('password').value = '';
        }
    </script>
</body>
</html>
