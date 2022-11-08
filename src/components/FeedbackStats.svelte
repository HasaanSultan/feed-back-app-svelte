<script>
  import { FeedbackStore } from "../store";

  $: count = $FeedbackStore.length;
  $: average = (
    $FeedbackStore.reduce((a, { rating }) => a + rating, 0) / count
  ).toFixed(2);
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
