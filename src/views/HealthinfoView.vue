<template>
  <NavBar />
  <router-view :key="$route.fullPath"/>
</template>

<script setup>
import 'bootstrap/dist/css/bootstrap.css';
import 'bootstrap/dist/js/bootstrap';
import NavBar from '@/components/NavBar';
</script>

<style>
</style>