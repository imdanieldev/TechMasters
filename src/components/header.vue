<script>
export default {
    name: "header",
    data(){
        return{
            winpx: window.innerHeight
        }
    },
    methods: {
        goUp() {
            if (document.body.scrollTop > 120 || document.documentElement.scrollTop > 120) {
                window.scrollTo(0,0);
            }else{
                window.scrollTo(0,this.winpx);
            }
        }
    },
    mounted() {
        let btn = document.querySelector("#goUp");
        let replace = document.querySelector("#replace");
        window.addEventListener("scroll", () => {
            if (document.body.scrollTop > 120 || document.documentElement.scrollTop > 120) {
                btn.classList.remove("animate-bounce");
                btn.classList.add("fixed");
                btn.classList.add("bottom-5");
                btn.classList.add("right-5");
                btn.classList.remove("rotate-0");
                btn.classList.add("rotate-180");
                replace.classList.remove("hidden");
            } else {
                btn.classList.add("animate-bounce");
                btn.classList.remove("fixed");
                btn.classList.remove("bottom-5");
                btn.classList.remove("right-5");
                btn.classList.add("rotate-0");
                replace.classList.add("hidden");
                btn.classList.remove("rotate-180");

            }
        });
    }
}
</script>
<template>
    <header class="h-screen flex justify-center items-center flex-col">
        <a href="//t.me/Tech_Ma3ters" target="_blank"><h2 class="text-2xl md:text-6xl text-center">Tech Masters</h2></a>
        <p class="text-center mt-4 text-base md:text-lg px-2 md:px-0">
            A community of groups and channels related to technology in Telegram.
        </p>
        <div @click="goUp()" id="goUp" class="backdrop-blur mt-16 bg-green-500/10 py-3 px-3 rounded-full animate-bounce cursor-pointer rotate-0 hover:bg-green-500/[0.15]">
            <svg class="fill-green-500" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 16 16">
                <path fill-rule="evenodd"
                    d="M8 1a.5.5 0 0 1 .5.5v11.793l3.146-3.147a.5.5 0 0 1 .708.708l-4 4a.5.5 0 0 1-.708 0l-4-4a.5.5 0 0 1 .708-.708L7.5 13.293V1.5A.5.5 0 0 1 8 1z" />
            </svg>
        </div>
        <div id="replace" class="hidden py-3 mt-16">
            <div class="w-6 h-6 opacity-0"></div>
        </div>
    </header>
</template>
