<script>
  import LeagueHeaderRow from "./LeagueHeaderRow.svelte";
  import LeagueRow from "./LeagueRow.svelte";

  let colors = ["red", "blue", "green"];

  let leagueEntries = [
    {
      id: Math.floor(Math.random() * 100000),
      color: colors[Math.floor(Math.random() * 3)],
      name: "Maths Warriors",
      score: 30 + Math.floor(Math.random() * 70)
    },
    {
      id: Math.floor(Math.random() * 100000),
      color: colors[Math.floor(Math.random() * 3)],
      name: "Amazing Adders",
      score: 30 + Math.floor(Math.random() * 70)
    },
    {
      id: Math.floor(Math.random() * 100000),
      color: colors[Math.floor(Math.random() * 3)],
      name: "Superstar crocodiles",
      score: 30 + Math.floor(Math.random() * 70)
    },
    {
      id: Math.floor(Math.random() * 100000),
      color: colors[Math.floor(Math.random() * 3)],
      name: "Mathletic Superstars",
      score: 30 + Math.floor(Math.random() * 70)
    },
    {
      id: Math.floor(Math.random() * 100000),
      color: colors[Math.floor(Math.random() * 3)],
      name: "Team Mathsosaurus - Rex",
      score: 30 + Math.floor(Math.random() * 70)
    },
    {
      id: Math.floor(Math.random() * 100000),
      color: colors[Math.floor(Math.random() * 3)],
      name: "Bloodcurdling Maths Masters",
      score: 30 + Math.floor(Math.random() * 70)
    },
    {
      id: Math.floor(Math.random() * 100000),
      color: colors[Math.floor(Math.random() * 3)],
      name: "The Mathematicians",
      score: 30 + Math.floor(Math.random() * 70)
    },
    {
      id: Math.floor(Math.random() * 100000),
      color: colors[Math.floor(Math.random() * 3)],
      name: "The Calculators",
      score: 30 + Math.floor(Math.random() * 70)
    },
    {
      id: Math.floor(Math.random() * 100000),
      color: colors[Math.floor(Math.random() * 3)],
      name: "The Number group",
      score: 30 + Math.floor(Math.random() * 70)
    }
  ];
  let newTeams = [
    {
      id: Math.floor(Math.random() * 100000),
      color: "blue",
      name: "Team Red",
      score: 30 + Math.floor(Math.random() * 70)
    },
    {
      id: Math.floor(Math.random() * 100000),
      color: "green",
      name: "Team Green",
      score: 30 + Math.floor(Math.random() * 70)
    },
    {
      id: Math.floor(Math.random() * 100000),
      color: "red",
      name: "Team Blue",
      score: 30 + Math.floor(Math.random() * 70)
    }
  ];
  let orderedEntries = [...newTeams, ...leagueEntries]
    .sort((a, b) => b.score - a.score)
    .reduce((acc, val, ind) => {
      if(ind === 0){
        return [{...val, pos: 1}]
      }
      const isLess = val.score < acc[acc.length - 1]?.score;
      console.log('isLess', isLess)
      console.log('pos: acc[acc.length-1].pos', acc[acc.length-1].pos + isLess ? 10 : 20)
      return [
        ...acc,
        {
          ...val,
          pos: acc[acc.length-1].pos + (isLess ? 1 : 0)
        }
      ];
    }, []);
</script>

<style>
  .league-table {
    flex: 1;
    height: 100%;
  }
</style>

<table class="league-table">
  <LeagueHeaderRow />
  {#each orderedEntries as leagueEntry}
    <LeagueRow {...leagueEntry} />
  {/each}
</table>
