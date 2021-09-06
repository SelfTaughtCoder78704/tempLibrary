<script>
  export let listBlockContent = {};
</script>

{#if listBlockContent.items.length > 0}
  <div
    class="list-block {listBlockContent.classes} {$$props.class}"
    id={listBlockContent.id || ""}
  >
    <ul>
      {#each listBlockContent.items as list}
        {#if list.listItemIcon}
          <li class="icon-list-item">
            <img src={list.listItemIcon} alt={list.text} />
            <span class="list-text">
              {list.text}
            </span>
          </li>
        {:else}
          <li>
            <span class="list-text">
              {list.text}
            </span>
          </li>
        {/if}
      {/each}
    </ul>
  </div>
{/if}

<style>
  .list-block {
    margin: 0;
    padding: 0;
  }
  .list-block ul {
    width: fit-content;
    margin: 0;
    padding: 0;
    list-style: none;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
  }
  .list-block li {
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .icon-list-item img {
    width: 20px;
  }
</style>
