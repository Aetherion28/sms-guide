# Country Leaderboard

This leaderboard shows the top players grouped by country (first 5 per country).

<table id="leaderboard">
  <thead>
    <tr>
      <th>Country</th>
      <th>First</th>
      <th>Second</th>
      <th>Third</th>
      <th>Fourth</th>
      <th>Fifth</th>
    </tr>
  </thead>
  <tbody></tbody>
</table>

<script>
const API_URL = "https://www.speedrun.com/api/v2/GetGameLeaderboard2?_r=eyJwYXJhbXMiOnsiY2F0ZWdvcnlJZCI6Im4yeTNyOGRvIiwiZW11bGF0b3IiOjEsImdhbWVJZCI6InYxcHhqejY4Iiwib2Jzb2xldGUiOjAsInBsYXRmb3JtSWRzIjpbXSwicmVnaW9uSWRzIjpbXSwidGltZXIiOjAsInZlcmlmaWVkIjoxLCJ2YWx1ZXMiOlt7InZhcmlhYmxlSWQiOiJqODQ1bWQ0biIsInZhbHVlSWRzIjpbImdxN29uMHZsIl19LHsidmFyaWFibGVJZCI6InlscXhnejc4IiwidmFsdWVJZHMiOlsiMWduNHJ6OGwiXX1dLCJ2aWRlbyI6MH0sInBhZ2UiOjEsInZhcmyI6MTc3MTY0Mzg5N30";

async function fetchLeaderboardPage(page = 1) {
  try {
    const url = new URL(API_URL);
    url.searchParams.set('page', page);
    const res = await fetch(url);
    const data = await res.json();
    if (!data.playerList) return [];
    return data.playerList;
  } catch (err) {
    console.error("Error fetching page", page, err);
    return [];
  }
}

async function fetchAllPlayers() {
  let allPlayers = [];
  const MAX_PAGE = 11;
  for (let page = 1; page <= MAX_PAGE; page++) {
    const players = await fetchLeaderboardPage(page);
    if (!players.length) break;
    allPlayers = allPlayers.concat(players);
  }
  return allPlayers;
}

function getCountryName(code) {
  try {
    const countryCode = code.split('/')[0];
    const regionNames = new Intl.DisplayNames(['en'], {type: 'region'});
    return regionNames.of(countryCode.toUpperCase()) || countryCode;
  } catch {
    return code;
  }
}

function buildLeaderboardTable(players) {
  const countries = {};
  players.forEach(player => {
    if (!player.areaId) return;
    const country = getCountryName(player.areaId);
    if (!countries[country]) countries[country] = [];
    countries[country].push(player.name);
  });

  const tbody = document.querySelector("#leaderboard tbody");
  tbody.innerHTML = "";

  Object.entries(countries).forEach(([country, names]) => {
    const row = document.createElement("tr");
    row.innerHTML = `<td>${country}</td>` +
      names.slice(0,5).map(n => `<td>${n}</td>`).join('');
    tbody.appendChild(row);
  });
}

async function main() {
  const players = await fetchAllPlayers();
  buildLeaderboardTable(players);
}

main();
</script>
