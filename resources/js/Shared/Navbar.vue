<template>
    <div class="flex flex-row justify-between align-center w-full">
        <Link href="/" class="logo"><img src="img/gayrimesgul_light.png" alt=""></Link>
       <div class="flex flex-row justify-start align-center">
        <NavLink :active="$page.component === 'App'" href="/" :title="'Anasayfa'"/>
        <NavLink :active="$page.component === 'Takvim'" href="/takvim" :title="'Takvim'"/>
        <NavLink :active="$page.component === 'Oyuncular'" href="/oyuncular" :title="'Oyuncular'"/>
       </div>
        <NavLink :active="$page.component === 'Iletisim'" href="/iletisim" :title="'İletişim'" class="primary"/>

    </div>
</template>

<script>
import { Link } from "@inertiajs/inertia-vue3";
import NavLink from './NavLink.vue';

export default {
    components: { Link, NavLink },
    props: ["name"],
    data() {
        return {};
    },
};
</script>

<style scoped>
.logo{
        border-radius: 100px;
        background-color: #F5F5F550;

        display: flex;
        justify-content: center;
        align-items: center;
    }
    .logo:hover{
        background-color: var(--color-one);
    }
    .primary{
        color: var(--color-two);
    }
    .primary:hover{
        color: var(--color-one);
    }
    img{
        width: 100px;
    }
</style>
