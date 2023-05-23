<template>
  <div class="sidebar" :class="{pushMainContent: isActive}" @click="isActive=!isActive">
    <img src="/public/menu-icon.svg">
  </div>
  <div id="mySidenav" class="sidenav" :class="{openNavClass: isActive}">
    <a class="closebtn" @click="isActive=!isActive">&times;</a>
    <div class="sidebar-categories">
      <a>
        После ремонта
      </a>
      <a>
        Генеральная уборка
      </a>
      <a>
        Регулярная уборка
      </a>
      <a>
        Мойка окон
      </a>
      <a>
        +380 67 401 69 77
      </a>
    </div>
    <a>Про нас</a>
    <a>Про нас</a>
    <a>Про нас</a>
  </div>
</template>

<script>
export default  {
  data() {
    return {
      isActive: false
    };
  }
}
</script>

