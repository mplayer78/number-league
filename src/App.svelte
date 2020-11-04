<script>
  export let name;
  import HeaderBar from "./HeaderBar.svelte";
  import VideoBox from "./VideoBox.svelte";
  import ScoreLeague from "./ScoreLeague.svelte";
  import Interaction from "./Interaction.svelte";
  import FooterBar from "./FooterBar.svelte";
</script>

<style>
  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }

  .content {
    display: flex;
    width: 100%;
    align-items: stretch;
    gap: var(--large-padding);
    margin-top: var(--x-large-padding);
  }
</style>

<svelte:head>
  <link
    href="https://fonts.googleapis.com/css2?family=Quicksand:wght@400;600&display=swap"
    rel="stylesheet" />
</svelte:head>

<main>
  <HeaderBar />
  <div class="content">
    <VideoBox />
    <ScoreLeague />
  </div>
  <Interaction />
  <FooterBar />
</main>
