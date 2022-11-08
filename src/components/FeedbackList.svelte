<script>
  // import { onDestroy, onMount } from "svelte";
  import { FeedbackStore } from "../store";

  import { scale, fade } from "svelte/transition";
  import FeedbackItem from "./FeedbackItem.svelte";

  // let feedback = [];
  // export let feedback = [];

  // const unSubcribe = (FeedbackStore.subscribe = (data) => (feedback = data));

  // onMount(() => {
  //   console.log("Mounting...");
  // });

  // onDestroy(() => {
  //   unSubcribe();
  // });
</script>

{#each $FeedbackStore as fb (fb.id)}
  <div in:scale out:fade={{ duration: 500 }}>
    <FeedbackItem item={fb} on:delete-feedback />
  </div>
{/each}
