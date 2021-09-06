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

<style type="text/scss">
  .cta-block {
    margin-right: auto;
    margin-left: auto;

    .cta-fine-print {
      margin-top: 15px;
      text-align: center;
    }
  }

  .cta-wrapper {
    display: inline-block;
  }

  .btn {
    -webkit-appearance: none;
    padding: 1rem;
    display: inline-block;
    background: rgb(204, 202, 202);
    color: white;
    font-size: 14px;
    line-height: 1;
    text-align: center;
    text-decoration: none;
    font-family: sans-serif;
    transition: color 300ms, black 300ms, grey 300ms;

    &:hover {
      background: rgb(182, 180, 180);
      color: white;
    }

    &:focus {
      outline: none;
      box-shadow: none;
    }
  }

  .btn-small {
    font-size: s(1.5);
    padding: s(2);
  }
</style>
