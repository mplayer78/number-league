<script>
  export let id, name, color, score, pos;
</script>

<style>
  td {
    vertical-align: middle;
    padding: var(--small-padding) var(--med-padding);
  }
  .score {
    font-weight: 600;
    font-size: 1.2rem;
  }
  svg {
    height: 40px;
  }
  text {
    font-size: 50px;
    text-anchor: middle;
    dominant-baseline: middle;
    font-weight: 600;
  }
  .star_path {
    fill: none;
    stroke-width: 2;
    stroke: var(--dark-grey);
  }
  .pos-1 {
    fill: var(--nf-gold);
  }
  .pos-2 {
    fill: var(--nf-silver);
  }
  .pos-3 {
    fill: var(--nf-bronze);
  }
</style>

<tr class="league-table_row">
  <td class="star">
    <svg viewBox="0 0 124 114">
      <path
        class={`star_path ${'pos-' + pos}`}
        d="M62 0L81.4851 37.0063L123.819 43.5319L93.5275 72.9287L100.206
        113.968L62 95.13L23.794 113.968L30.4725 72.9287L0.181328 43.5319L42.5149
        37.0063L62 0Z" />
      <text x="62" y="57">{pos}</text>
    </svg>
  </td>
  <td class="color-blob">
    <svg viewBox="0 0 101 101">
      <circle cx="51" cy="51" r="40" style="fill: {color}" />
    </svg>
  </td>
  <td class="team-name">{name}</td>
  <td class="score">{score}</td>
</tr>
