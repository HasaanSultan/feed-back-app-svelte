<script>
  import FeedbackForm from "./components/FeedbackForm.svelte";
  import FeedbackList from "./components/FeedbackList.svelte";
  import FeedbackStats from "./components/FeedbackStats.svelte";
  let feedback = [
    {
      id: 1,
      rating: 10,
      text: "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters,",
    },
    {
      id: 2,
      rating: 8,
      text: "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters,",
    },
    {
      id: 3,
      rating: 5,
      text: "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters,",
    },
  ];

  $: count = feedback.length;
  $: average = (
    feedback.reduce((a, { rating }) => a + rating, 0) / count
  ).toFixed(2);

  const handleSubmit = (e) => {
    feedback = [...feedback, e.detail];
  };

  const deleteFeedback = (e) => {
    feedback = feedback.filter((x) => x.id !== e.detail);
  };
</script>

<main class="container">
  <FeedbackForm on:add-feedback={handleSubmit} />
  <FeedbackStats {count} {average} />
  <FeedbackList {feedback} on:delete-feedback={deleteFeedback} />
</main>
