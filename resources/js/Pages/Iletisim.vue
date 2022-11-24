<template>
    <div class="flex flex-col justify-start sm:items-center items-start">
        <p class="title w-full">Bize Ulaşın</p>
        <div class="social">
            <p>Sosyal Medya Hesabımız</p>
            <button @click="handleClick" class="instagram"><i class="bi bi-instagram text-4xl"></i>@gayrimesgul2021</button>
        </div>
        <form action="" class="iletisimFormu w-full">
            <p class="col-span-2 text-xl">İletişim Formu</p>
            <input type="email" placeholder="Email" class="w-full inputs col-span-2" required/>
            <textarea
                rows="3"
                placeholder="Mesajınız.."
                class="col-span-2 inputs" required
            ></textarea>
            <button
                class="w-full col-span-2 sendBtn disabled:opacity-25"
                disabled
            >
                Gönder
            </button>
        </form>
    </div>
</template>

<script>
import { Link } from "@inertiajs/inertia-vue3";

export default {
    components: { Link },
    methods:{
        handleClick() {
            window.open("https://www.instagram.com/gayrimesgul2021");
        }
    }
};
</script>

<style scoped>
.title {
    font-size: 72px;
    font-weight: 700;
    color: var(--color-one);
    margin-bottom: 24px;
}

.iletisimFormu {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    box-shadow: 6px 6px 30px -7px var(--color-four),
        -6px -6px 30px -15px var(--color-one);
    padding: 24px;
    background-color: rgb(18, 18, 18, 0.7);
    border-radius: 15px;
}

.inputs {
    padding: 8px 16px;
    border: none;
    font-size: 16px;
    color: var(--color-two);
    background-color: transparent;
    border-bottom: 1px solid var(--color-one);
}

.inputs:focus-visible {
    outline: none;
    border-bottom-color: var(--color-two);
    border-bottom-width: 2px;
}

.sendBtn {
    padding: 8px 16px;
    margin: 8px 0px;
    background-color: var(--color-three);
    border-radius: 4px;
    color: var(--color-four);
    font-weight: 700;
    font-size: 16px;
}

.sendBtn:hover {
    background-color: var(--color-two);
    box-shadow: 1px 1px 20px -5px var(--color-two);
    color: var(--color-one);
}

.social {
    display: flex;
    flex-direction: column;
    gap: 16px;
    box-shadow: 6px 6px 30px -7px var(--color-four),
        -6px -6px 30px -15px var(--color-one);
    padding: 24px;
    background-color: rgb(18, 18, 18, 0.7);
    border-radius: 15px;
    margin: 20px 0;
}
.instagram{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: flex-start;
    color: var(--color-one);
    font-size: 24px;
    gap: 16px;
    
}
.instagram i{
    color: var(--color-two);
}
.instagram:hover{
    background-color: transparent;
}
p{
    color: var(--color-two);
    font-size: 16px;
}

@media only screen and (max-width: 520px) {
    .title {
        font-size: 52px;
    }
    .social{
        width: 100%;
    }
}
</style>
