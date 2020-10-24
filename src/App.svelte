<script>
  import Header from "./components/Header.svelte";
  import Footer from "./components/Footer.svelte";
  import Tabs from "./shared/Tabs.svelte";
  import CreatePollForm from './components/CreatePollForm.svelte'

  // tabs
  let items = ["Current Polls", "Add New Poll"];
  let activeItem = "Current Polls";

  const handleTabChange = (e) => {
    activeItem = e.detail;
  };
</script>

<style>
  main {
    max-width: 960px;
    margin: 40px auto;
  }
</style>

<Header />
<main>
  <Tabs on:tabChange={handleTabChange} {items} {activeItem} />
  {#if activeItem === 'Current Polls'}
    <p>Poll List Component goes here</p>
  {:else if activeItem === 'Add New Poll'}
    <CreatePollForm />
  {/if}
</main>
<Footer />
