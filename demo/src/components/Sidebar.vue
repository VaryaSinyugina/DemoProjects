<template>
  <aside class="sidebar-menu">
    <h2>Demo Test</h2>
    <ul>
      <li>
        <img src="@/assets/user.png" alt="Profile" />
        <a href="#">Profile</a>
      </li>
      <li>
        <img src="@/assets/rim.png" alt="Vechicles" />
        <a href="#">Vechicles</a>
      </li>
      <li>
        <img src="@/assets/settings.png" alt="Setting" />
        <a href="#">Setting</a>
      </li>
    </ul>
    <div class="image-container">
      <img src="@/assets/wave.png" alt="Wave" />
    </div>
  </aside>
</template>

<script>
export default {
  name: 'SidebarMenu',
  data() {
    return {
        //
    };
  },
};
</script>

<style scoped>
.sidebar-menu {
  width: 256px;
  background-color: #282828;
  color: #ffffff;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 100vh;
}

.sidebar-menu h2 {
  line-height: 24px;
  font-weight: 700;
  font-size: 24px;
  margin-top: 30px;
  margin-left: 56px;
}

.sidebar-menu ul {
  list-style-type: none;
  padding: 0;
  margin: 156.55px 0 0 0;
  width: 100%;
}

.sidebar-menu ul li {
  margin: 10px 0;
  display: flex;
  align-items: center;
  padding: 10px 20px;
  cursor: pointer;
  transition: background-color 0.3s, border-left 0.3s;
}

.sidebar-menu ul li:hover {
  background-color: #ffffff33;
  border-left: 2px solid #D90E32;
}

.sidebar-menu ul li a {
  width: 154px;
  height: 24px;
  text-decoration: none;
  color: #ffffff73;
  font-size: 16px;
  font-weight: 500;
}

.sidebar-menu ul li img {
  width: 24px;
  height: 24px;
  margin-right: 20px;
}

.image-container {
  text-align: center;
  margin-top: auto;
}

.image-container img {
  max-width: 100%;
  height: auto;
  border-radius: 10px;
}
</style>