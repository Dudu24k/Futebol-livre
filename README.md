<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Futebol Livre</title>
  <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
</head>
<body class="bg-gray-100 text-gray-900">
  <header class="bg-green-600 text-white p-4 text-center text-2xl font-bold">
    Futebol Livre - Jogos Gratuitos e Legais
  </header>

  <section class="p-4">
    <h2 class="text-xl font-semibold mb-2">Jogos ao Vivo Agora</h2>
    <div class="bg-white p-4 rounded shadow">
      <p class="text-green-600 font-bold">AO VIVO</p>
      <p>Flamengo x Palmeiras - <a href="https://www.youtube.com/c/CazéTV" class="text-blue-500 underline" target="_blank">Assista na CazéTV</a></p>
    </div>
  </section>

  <section class="p-4">
    <h2 class="text-xl font-semibold mb-2">Agenda da Semana</h2>
    <ul class="space-y-2">
      <li class="bg-white p-3 rounded shadow">
        10/04 - Corinthians x Santos - 19h00 - <a href="https://www.youtube.com/@paulistao" class="text-blue-500 underline" target="_blank">YouTube Paulistão</a>
      </li>
      <li class="bg-white p-3 rounded shadow">
        11/04 - Grêmio x Inter - 20h30 - <a href="https://tntsports.com.br/" class="text-blue-500 underline" target="_blank">TNT Sports (Gratuito)</a>
      </li>
    </ul>
  </section>

  <section class="p-4">
    <h2 class="text-xl font-semibold mb-2">Buscar por Time</h2>
    <input type="text" placeholder="Digite o nome do time" class="w-full p-2 border border-gray-300 rounded mb-4" oninput="filterGames(this.value)">
    <div id="results" class="space-y-2"></div>
  </section>

  <script>
    const games = [
      { team: "Corinthians", game: "Corinthians x Santos - 10/04 - 19h00", link: "https://www.youtube.com/@paulistao" },
      { team: "Grêmio", game: "Grêmio x Inter - 11/04 - 20h30", link: "https://tntsports.com.br/" },
      { team: "Flamengo", game: "Flamengo x Palmeiras - AO VIVO", link: "https://www.youtube.com/c/CazéTV" }
    ];

    function filterGames(query) {
      const results = document.getElementById('results');
      results.innerHTML = '';
      if (!query) return;
      const filtered = games.filter(g => g.team.toLowerCase().includes(query.toLowerCase()));
      filtered.forEach(g => {
        const el = document.createElement('div');
        el.className = 'bg-white p-3 rounded shadow';
        el.innerHTML = `${g.game} - <a href="${g.link}" class="text-blue-500 underline" target="_blank">Assistir</a>`;
        results.appendChild(el);
      });
    }
  </script>
</body>
</html>
