<style>
  .jumbo {
    padding: 50px;
    background: #f6f6f6;
  }
  .right {
    float: right;
  }

  .svelte {
    background: url(/logo.svg) no-repeat;
    background-size: contain;
    height: 200px;
    width: 200px;
    top: -25px;
  }

</style>
<div class="jumbo">
  <div class="right svelte"></div>
  <slot></slot>
</div>
