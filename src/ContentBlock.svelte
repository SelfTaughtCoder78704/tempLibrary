<script>
  import CtaBlock from "./CtaBlock.svelte";

  export let contentBlockContent = {};
</script>

{#if contentBlockContent.body}
  <div
    class="content-block {contentBlockContent.classes || ''} {$$props.class}"
    id={contentBlockContent.id || ""}
  >
    {#each contentBlockContent.body as component}
      {#if component.block === "text"}
        'Text'
      {/if}
      {#if component.block === "title"}
        {component.title}
      {/if}
      {#if component.block === "ListBlock"}
        'List Block'
      {/if}
      {#if component.block === "CtaBlock"}
        <CtaBlock
          ctaContent={{
            ctaText: component.ctaText,
            ctaLink: component.ctaLink,
            classes: component.classes,
            btnClasses: component.btnClasses,
            trackable: component.trackable,
            ctaFinePrint: component.ctaFinePrint,
            ctaRel: component.ctaRel,
            id: component.id,
          }}
        />
      {/if}
      {#if component.block === "QuoteBlock"}
        "Quote Block"
      {/if}
      {#if component.block === "MediaBlock"}
        "Media Block"
      {/if}
    {/each}
  </div>
{/if}
