<template>
    <div class="flex flex-row justify-between align-center w-full">
        <Link href="/" class="logo"
            ><img src="img/gayrimesgul_light.png" alt=""
        /></Link>
        <button @click="showMenu" class="menuBtn">
            <i class="bi bi-list text-7xl"></i>
        </button>
    </div>
    <div class="closeMenu" v-if="showNav" @click.self="showMenu">
        <div class="mobileMenu" :class="{ open: showNav }">
            <Link href="/" class="logo logoMobile"
                ><img src="img/gayrimesgul_light.png" alt=""
            /></Link>

            <NavLink
                :active="$page.component === 'App'"
                href="/"
                :title="'Anasayfa'"
            />
            <NavLink
                :active="$page.component === 'Takvim'"
                href="/takvim"
                :title="'Takvim'"
            />
            <NavLink
                :active="$page.component === 'Oyuncular'"
                href="/oyuncular"
                :title="'Oyuncular'"
            />

            <NavLink
                :active="$page.component === 'Iletisim'"
                href="/iletisim"
                :title="'İletişim'"
                class="primary"
            />
        </div>
    </div>
</template>

<script>
import { Link } from "@inertiajs/inertia-vue3";
import NavLink from "./NavLink.vue";

export default {
    components: { Link, NavLink },
    data() {
        return {
            showNav: false,
        };
    },

    methods: {
        showMenu() {
            this.showNav = !this.showNav;
        }
    },
};
</script>

<style scoped>
.logo {
    width: 72px;
    height: 72px;
    border-radius: 100%;
    background-color: #f5f5f550;
    display: flex;
    justify-content: center;
    align-items: center;
}
.logo:hover {
    background-color: var(--color-one);
}
.primary {
    color: var(--color-two);
}
.primary:hover {
    color: var(--color-one);
}
.logo img {
    width: 68px;
    height: 68px;
}
/* Mobile */
.closeMenu{
    width: 100%;
    height: 100%;
    position: fixed;
    top: 0;
    left: 0;
    bottom: 0;
    z-index: 1;

}
.mobileMenu {
    position: fixed;
    padding: 36px 44px;
    top: 0;
    left: -50%;
    bottom: 0;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: flex-start;

    width: 50%;
    height: 100%;
    background-color: #121212f0;
    backdrop-filter: blur(10px);

    transition: cubic-bezier(0.16, 0.24, 0.12, 0.98);
    animation-name: slide;
    animation-duration: 1s;
}
.open {
    transform: translateX(100%);
}
@keyframes slide {
    from {
        transform: translateX(0);
    }
    to {
        transform: translateX(100%);
    }
}
.logoMobile {
    width: 120px;
    height: 120px;

    margin: 30px 34px;
}
.logoMobile img {
    width: 90%;
    height: 90%;
}
@media only screen and (max-width: 520px) {
    .mobileMenu {
        width: 80%;
        left: -80%;
    }
    @keyframes slide {
        from {
            transform: translateX(0);
        }
        to {
            transform: translateX(100%);
        }
    }

    .logoMobile {
        width: 120px;
        height: 120px;

        margin: 30px 34px;
    }
    .logoMobile img {
        width: 90%;
        height: 90%;
    }
}
.menuBtn:hover {
    background-color: transparent;
}
.menuBtn:active {
    color: var(--color-three);
    box-shadow: inset -3px -3px 7px var(--color-one),
        inset 3px 3px 4px var(--color-four);
    transition: 50ms ease-in-out;
}
</style>
