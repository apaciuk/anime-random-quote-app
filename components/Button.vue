<template>

<button id="button" @click="reloadPage()">Refresh</button>
</template>
<script>
export default {
 methods: {
  reloadPage(){
    window.location.reload()
  }
}
}
</script>

<style>

</style>