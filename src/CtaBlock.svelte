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
    padding: s(2.5);
    display: inline-block;
    background: $primary;
    color: $white;
    font-size: s(2);
    line-height: 1;
    text-align: center;
    text-decoration: none;
    font-family: $font-button;
    transition: color 300ms, border-color 300ms, background-color 300ms;

    &:hover {
      background: lighten($primary, 8%);
      color: $white;
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
