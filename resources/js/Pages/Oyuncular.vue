<template>
    <p class="header mb-8">Oyuncular</p>
    <div class="oyuncular">
        <div class="oyuncu" @mouseenter="handleHover" @mouseleave="handleBack">
                <img src="img/oyuncular/asya.jpeg" alt="" />
                <div class="oyuncuInfo " :class="{ infoHover: oyuncuHovered }">
                    <p
                        class="oyuncuName"
                        :class="{ oyuncuNameHover: oyuncuHovered }"
                    >
                        Asya Bozarslan
                    </p>
            </div>
        </div>
        <div class="oyuncu" @mouseenter="handleHover" @mouseleave="handleBack">
                <img src="img/oyuncular/asya.jpeg" alt="" />
                <div class="oyuncuInfo">
                    <p
                        class="oyuncuName"
                        :class="{ oyuncuNameHover: oyuncuHovered }"
                    >
                        Asya Bozarslan
                    </p>
            </div>
        </div>
        <div class="oyuncu" @mouseenter="handleHover" @mouseleave="handleBack">
                <img src="img/oyuncular/asya.jpeg" alt="" />
                <div class="oyuncuInfo">
                    <p
                        class="oyuncuName"
                        :class="{ oyuncuNameHover: oyuncuHovered }"
                    >
                        Asya Bozarslan
                    </p>
            </div>
        </div>
        <div class="oyuncu" @mouseenter="handleHover" @mouseleave="handleBack">
                <img src="img/oyuncular/asya.jpeg" alt="" />
                <div class="oyuncuInfo">
                    <p
                        class="oyuncuName"
                        :class="{ oyuncuNameHover: oyuncuHovered }"
                    >
                        Asya Bozarslan
                    </p>
            </div>
        </div>
    </div>
    <p class="header mt-16 mb-8">Moderatör</p>
</template>

<script>
export default {
    data() {
        return {
            oyuncuHovered: false,
        };
    },
    methods: {
        handleHover() {
            this.oyuncuHovered = true;
        },
        handleBack() {
            this.oyuncuHovered = false;
        },
    },
};
</script>

<style scoped>
.header {
    font-size: 36px;
}
.oyuncular {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    flex-wrap: wrap;
}
.oyuncu {
    display: block;
    margin: 10px 10px;
}
.oyuncuInfo {
    position: fixed;
    padding: 8px;
    width: 200px;
    height: 100px;
    border-radius: 0 0 20px 20px;
    background-color: #121212a0;
    transform: translate(0px,-100px);
    opacity: 0;
    z-index: 2;
}
.infoHover{
    opacity: 1;
}
.oyuncu:hover {
    transform: scale(1.2);
    /* padding: 8px; */
    z-index: 2;
    /* background-color: #12121250; */
    border-radius: 25px;
    box-shadow: -3px -3px 25px -16px var(--color-one),3px 3px 30px -16px var(--color-four);
}
.oyuncuName {
    transform: translate(0px,50px);
    font-size: 16px;
    margin-top: 8px;
    opacity:0;
    z-index: 2;
}
.oyuncuNameHover {
    transition: cubic-bezier(0.16, 0.24, 0.12, 0.98);
    animation-name: slide;
    animation-duration: 1s;
    transform: translate(0px,0px);
    opacity: 1;
    z-index: 2;
}
@keyframes slide {
    from {
        transform: translate(0px,60px);
        z-index: -2;
        opacity: 0;

    }
    to {
        transform: translate(0px,0px);
        z-index: 2;
        opacity: 1;

    }
}

img {
    display: block;
    width: 200px;
    border-radius: 20px;
}
</style>
