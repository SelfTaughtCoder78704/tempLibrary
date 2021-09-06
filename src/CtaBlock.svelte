<script>
  export let ctaContent = {};
</script>

<div
  class="cta-block {ctaContent.classes || ''} {$$props.class}"
  id={ctaContent.id | ""}
>
  <div class="cta-wrapper">
    <a
      href={ctaContent.ctaLink}
      class=" btn {ctaContent.btnClasses || ''}"
      data-trackable={ctaContent.trackable || ""}
      data-interaction={ctaContent.interaction || ""}
      rel={ctaContent.ctaRel || ""}
    >
      {ctaContent.ctaText || ""}
    </a>

    {#if ctaContent.ctaFinePrint}
      <small class="cta-fine-print">{ctaContent.ctaFinePrint || ""}</small>
    {/if}
  </div>
</div>

<style>
  .content-block {
    padding: 10px 20px;

    text-align: left;
    margin-right: auto;
    margin-left: auto;
    max-width: 1440px;
  }
</style>
