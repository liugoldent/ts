<template>
  <div class="home">
    <div class="father">
      <div class="column">
        <img src="https://fakeimg.pl/266x200/ff0000/000">
        <p>中文中文中文中文中文中文中文中文中文中文中文
          中文中文中文中文中文中文中文中文中文中文中文
          中文中文中文中文中文中文中文中文中文中文中文
        </p>
      </div>
      <div class="column">
        <img src="https://fakeimg.pl/266x200/ff0000/000">
        <p>中文中文中文中文中文中文中文中文中文中文中文
          中文中文中文中文中文中文中文中文中文中文中文
          中文中文中文中文中文中文中文中文中文中文中文
        </p>
      </div>
      <div class="clear-float"></div>
    </div>
  </div>
</template>
<style scoped>
  .father{
    width: 600px;
    background-color: orange;
    opacity: 0.8;
    margin:auto;
  }

  .column{
    float:left;
    width:280px;
    margin:10px;
    padding:2px;
    /* padding:5px; */
    border:2px solid black;
    box-sizing: border-box;
  }
  .clear-float {
    clear:left;
  }
</style>

