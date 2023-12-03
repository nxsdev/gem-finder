<script lang="ts">
  import { onMount } from 'svelte';
  import { AppBar } from '@skeletonlabs/skeleton';

  let url = '';

  onMount(async () => {
    // examinations
    url = 'http://localhost:3000/diagnosis';
  });

  function handleClick() {
    // ボタンがクリックされたときの処理を書く
    // ここでは仮に新しいタブでURLを開く処理を書きます
    window.open(url, '_blank');
  }
</script>

<AppBar>
  <svelte:fragment slot="lead">(icon)</svelte:fragment>
  <svelte:fragment slot="trail">(actions)</svelte:fragment>
  <svelte:fragment slot="headline">(headline)</svelte:fragment>
</AppBar>
<div class="container mx-auto p-8 space-y-8">
  <h1 class="h1">Gem Finder</h1>
  <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
  <section>
    <div class="flex">
      <div class="card p-4">Basic</div>
      <div class="card p-4">Basic</div>
      <div class="card p-4">Basic</div>
    </div>
    <button on:click={handleClick} class="btn variant-filled-primary">今すぐ診断</button>
    <a href="/examinations" class="btn variant-filled-primary">今すぐ診断2</a>
  </section>
</div>
