<template>
  <div id="container" class="wrapper">
    <div v-for="timeEight in eights" class="box-8">
      <div class="number">
        {{ timeEight }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      eights: []
    }
  },
  created: function () {
    for (let a = 8; a <= 2208; a = a + 8) {
      this.eights.push(a)
    }
  }
}
</script>

<style>

  .box-8 {
    width: calc((100% - 24px) / 12);
    height: 48px;
    background: #111111;
    border: 1px solid rgba(45,45,45,0.15);
    display: flex;
    justify-content: center;
    align-items: center;
    transition: all 0.06s ease-in-out;
    padding: 12px;
  }

  .box-8:hover{
      background:rgba(45,45,45,0.5);
      border: 1px solid rgba(100,199,255,0.4);
      transform: scale(1.5);
  }

  .wrapper {
    background: #101010;
    display: flex;
    flex-wrap: wrap;
    padding: 24px;
  }

  .number {
    font-size:1rem;
    line-height:1.5rem;
    color: #666666;
    text-align: center;
  }

  .box-8:hover .number{
      color:#6699ff;
      font-weight: 700;
  }
</style>
