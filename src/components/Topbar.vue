<template>
  <div class="topbar">
      <div class="logo">
          VueResumer
      </div>
      <div class="buttons">
          <button>注册</button>
          <button>登录</button>
      </div>
  </div>
</template>

<script>

</script>


<style lang="scss">
    .topbar{
        border: 1px solid black;
        min-height: 3rem;
        display: flex;
        align-items: center;
        justify-content: space-between;
        >.logo{
            margin-left: 16px;
        }
        >.buttons{
            margin-right: 32px;
        }
    }
</style>

