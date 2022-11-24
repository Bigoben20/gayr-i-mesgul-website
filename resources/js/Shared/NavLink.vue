<template>
  <Link class="Navlink" :class="{'nav-active': active}">{{title}}</Link>
</template>

<script>
import { Link } from "@inertiajs/inertia-vue3";

export default {
    props:['title','active'],
    components:{ Link }
}
</script>

<style>

</style>