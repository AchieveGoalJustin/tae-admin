<script lang="ts">
  import { fade } from "svelte/transition";
  import type { ModalState } from "../stores/modalControl";
  export let modalData: ModalState;
</script>

<div
  transition:fade
  class="bg-slate-800 text-white absolute z-50 text-sm rounded-md p-2 translate-x-80 lg:translate-x-64 xl:translate-x-64 -translate-y-6 shadow-md"
>
  {#if modalData.currentModal === "personal"}
    {#each modalData.personalErrors as error}
      <p>{`${error}にはエラーがあります`}</p>
    {/each}
  {/if}

  {#if modalData.currentModal === "campus"}
    {#each modalData.campusErrors as error}
      <p>{`${error}にはエラーがあります`}</p>
    {/each}
  {/if}

  {#if modalData.currentModal === "test"}
    {#each modalData.testErrors as error}
      <p>{`${error}にはエラーがあります`}</p>
    {/each}
  {/if}
</div>
