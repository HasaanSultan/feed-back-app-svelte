<script>
  export let count;
  export let average;
</script>

<div class="feedback-state">
  <h4>
    {count} Review
  </h4>
  <h4>Ratings Average : {average}</h4>
</div>

<style>
  .feedback-state {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
</style>
