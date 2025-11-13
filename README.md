# 1️⃣ Cria pasta do projeto e entra nela
mkdir criptomente-site
cd criptomente-site

# 2️⃣ Cria estrutura básica
mkdir assets css js pages

# 3️⃣ Cria arquivo index.html
cat > index.html <<'HTML'
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CriptoMente | Ganhe Dinheiro com Criptomoedas</title>
  <link rel="stylesheet" href="css/style.css">
</head>
<body>
  <header class="hero">
    <h1>💎 CriptoMente</h1>
    <p>Como ganhar dinheiro de verdade com criptomoedas</p>
    <nav>
      <a href="index.html">Início</a>
      <a href="pages/dicas.html">Dicas</a>
      <a href="pages/seguranca.html">Segurança</a>
      <a href="pages/estrategias.html">Estratégias</a>
      <a href="pages/futuro.html">Futuro</a>
    </nav>
  </header>

  <section class="intro">
    <h2>🧠 Mentalidade CriptoMente</h2>
    <p>Ganhar com criptomoedas não é sorte — é mentalidade, paciência e estratégia. Aqui você aprende o que realmente funciona.</p>
    <a href="pages/dicas.html" class="btn">Começar Agora</a>
  </section>

  <section class="quotes">
    <h2>✨ Frases de Líderes do Mercado</h2>
    <ul>
      <li>"Se não é sua chave, não é seu dinheiro." — Andreas Antonopoulos</li>
      <li>"A descentralização é uma das maiores inovações da internet." — CZ (Binance)</li>
      <li>"O tempo no mercado vence o timing do mercado." — Warren Buffett</li>
      <li>"Bitcoin é uma revolução tecnológica." — Elon Musk</li>
      <li>"Não se trata só de ficar rico — é sobre construir o futuro." — Vitalik Buterin</li>
    </ul>
  </section>

  <footer>
    <p>© 2025 CriptoMente | Siga-nos: @criptomente</p>
  </footer>

  <script src="js/main.js"></script>
</body>
</html>
HTML

# 4️⃣ Cria página de dicas
cat > pages/dicas.html <<'HTML'
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Dicas | CriptoMente</title>
  <link rel="stylesheet" href="../css/style.css">
</head>
<body>
  <header class="page-header">
    <h1>💡 Dicas para Ganhar Dinheiro com Cripto</h1>
  </header>
  <main>
    <h2>Passo a Passo CriptoMente</h2>
    <ol>
      <li>Aprenda o básico sobre blockchain e exchanges.</li>
      <li>Crie conta em uma corretora confiável (ex: Binance, OKX).</li>
      <li>Ative a autenticação 2FA antes de investir.</li>
      <li>Invista com DCA (Dollar Cost Averaging) — valores fixos mensais.</li>
      <li>Diversifique sua carteira: BTC, ETH e projetos sólidos.</li>
      <li>Use wallets seguras (cold wallets para longo prazo).</li>
      <li>Estude fundamentos antes de comprar altcoins.</li>
      <li>Evite promessas milagrosas de ganhos rápidos.</li>
      <li>Monitore o mercado com calma e paciência.</li>
      <li>Tenha metas e disciplina: o lucro vem do tempo e estratégia.</li>
    </ol>
    <a href="../index.html" class="btn">Voltar</a>
  </main>
</body>
</html>
HTML

# 5️⃣ Página de segurança
cat > pages/seguranca.html <<'HTML'
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Segurança | CriptoMente</title>
  <link rel="stylesheet" href="../css/style.css">
</head>
<body>
  <header class="page-header">
    <h1>🔐 Segurança no Mundo Cripto</h1>
  </header>
  <main>
    <ul>
      <li>Ative autenticação de dois fatores (2FA).</li>
      <li>Use senhas fortes e únicas para cada plataforma.</li>
      <li>Evite clicar em links suspeitos e phishing.</li>
      <li>Use cold wallets para armazenar valores altos.</li>
      <li>Nunca compartilhe suas chaves privadas.</li>
      <li>Lembre-se: “Se não é sua chave, não é seu dinheiro.”</li>
    </ul>
    <a href="../index.html" class="btn">Voltar</a>
  </main>
</body>
</html>
HTML

# 6️⃣ Página de estratégias
cat > pages/estrategias.html <<'HTML'
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Estratégias | CriptoMente</title>
  <link rel="stylesheet" href="../css/style.css">
</head>
<body>
  <header class="page-header">
    <h1>🚀 Estratégias de Lucro Cripto</h1>
  </header>
  <main>
    <ul>
      <li><strong>Holding:</strong> Comprar e segurar moedas fortes por longo prazo.</li>
      <li><strong>Trading:</strong> Lucros rápidos com compra e venda estratégica.</li>
      <li><strong>Staking e DeFi:</strong> Gere renda passiva deixando suas moedas trabalharem.</li>
      <li><strong>DCA:</strong> Invista um valor fixo mensal para reduzir risco.</li>
      <li><strong>Gestão de risco:</strong> Nunca invista mais do que pode perder.</li>
    </ul>
    <a href="../index.html" class="btn">Voltar</a>
  </main>
</body>
</html>
HTML

# 7️⃣ Página sobre o futuro
cat > pages/futuro.html <<'HTML'
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Futuro | CriptoMente</title>
  <link rel="stylesheet" href="../css/style.css">
</head>
<body>
  <header class="page-header">
    <h1>🌍 O Futuro do Dinheiro</h1>
  </header>
  <main>
    <p>As criptomoedas já são o presente — bancos, empresas e governos estão adotando o digital.</p>
    <ul>
      <li>Expansão das moedas digitais governamentais (CBDCs).</li>
      <li>Avanço das finanças descentralizadas (DeFi).</li>
      <li>Integração total entre bancos e blockchain.</li>
      <li>Oportunidades de emprego e investimento em Web3.</li>
    </ul>
    <blockquote>“O futuro pertence a quem entende o valor da descentralização.”</blockquote>
    <a href="../index.html" class="btn">Voltar</a>
  </main>
</body>
</html>
HTML

# 8️⃣ Cria CSS principal (Luxo Digital)
cat > css/style.css <<'CSS'
body {
  font-family: 'Poppins', sans-serif;
  margin: 0; padding: 0;
  background-color: #000;
  color: #f5f5f5;
}
header.hero {
  text-align: center;
  padding: 3rem 1rem;
  background: linear-gradient(135deg, #000 40%, #b99309);
  color: gold;
}
header.hero h1 { font-size: 3rem; margin: 0; }
header.hero nav a {
  margin: 0 10px; text-decoration: none;
  color: gold; font-weight: bold;
}
.btn {
  background-color: gold; color: #000;
  padding: 0.8rem 1.5rem;
  border-radius: 25px;
  display: inline-block;
  margin-top: 1rem;
  font-weight: bold;
}
section { padding: 2rem; text-align: center; }
footer {
  background: #111;
  color: #aaa;
  text-align: center;
  padding: 1rem;
  font-size: 0.9rem;
}
.page-header {
  background: #111;
  padding: 1.5rem;
  text-align: center;
  color: gold;
}
ul, ol { text-align: left; max-width: 700px; margin: auto; line-height: 1.8; }
blockquote {
  font-style: italic;
  color: #ccc;
  border-left: 4px solid gold;
  padding-left: 1rem;
}
CSS

# 9️⃣ Cria JS simples (interações futuras)
cat > js/main.js <<'JS'
console.log("CriptoMente – Site Luxo Digital iniciado");
JS
