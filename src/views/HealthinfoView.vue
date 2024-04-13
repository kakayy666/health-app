<template>
  <div class="health">
  <NavBar />
  <router-view :key="$route.fullPath" />
  <ContentBase>
    <div class="main">
    </div>
  </ContentBase>
</div>
</template>

<script setup>
import ContentBase from '../components/ContentBase';
import 'bootstrap/dist/css/bootstrap.css';
import 'bootstrap/dist/js/bootstrap';
import NavBar from '../components/NavBar';
</script>

<style scoped>
.main {
  width: 100%;
  height: 300px;
  display: flex;
  background-size: contain;
  background-repeat: no-repeat;
  border-radius: 20px;
  background-color: lightblue;
}

</style>