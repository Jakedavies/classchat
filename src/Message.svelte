<script>
  export let message;
  export let from;
  export let createdAt;
</script>

<style>
  .timestamp {
    font-weight: 200;
    text-transform: uppercase;
    margin-left: 8px;
    font-size: 0.8em;
  }
</style>

<main>
  <p>
    <b>{from}</b>
    <span class="timestamp">{createdAt} AM</span>
    <br />
    {message}
  </p>
</main>
