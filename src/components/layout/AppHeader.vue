<template>
    <header
        class="flex justify-evenly w-full lg:w-1000 my-0 mx-auto pt-2 text-center"
    >
        <div class="flex flex-col justify-between text-2xl md:text-3xl">
            <div class="flex justify-center lg:justify-start items-center">
                <h1 class="font-bold mt-3 mr-2">Pomodoro</h1>
                <svg
                    class="fill-white m-0 -mb-3 h-10 md:h-12 w-12"
                    version="1.1"
                    x="0px"
                    y="0px"
                    width="47.001px"
                    height="47.001px"
                    viewBox="0 0 47.001 47.001"
                    style="enable-background: new 0 0 47.001 47.001"
                    xml:space="preserve"
                >
                    <path
                        d="M46.907,20.12c-0.163-0.347-0.511-0.569-0.896-0.569h-2.927C41.223,9.452,32.355,1.775,21.726,1.775
                        C9.747,1.775,0,11.522,0,23.501C0,35.48,9.746,45.226,21.726,45.226c7.731,0,14.941-4.161,18.816-10.857
                        c0.546-0.945,0.224-2.152-0.722-2.699c-0.944-0.547-2.152-0.225-2.697,0.72c-3.172,5.481-9.072,8.887-15.397,8.887
                        c-9.801,0-17.776-7.974-17.776-17.774c0-9.802,7.975-17.776,17.776-17.776c8.442,0,15.515,5.921,17.317,13.825h-2.904
                        c-0.385,0-0.732,0.222-0.896,0.569c-0.163,0.347-0.11,0.756,0.136,1.051l4.938,5.925c0.188,0.225,0.465,0.355,0.759,0.355
                        c0.293,0,0.571-0.131,0.758-0.355l4.938-5.925C47.018,20.876,47.07,20.467,46.907,20.12z"
                    ></path>
                    <path
                        d="M21.726,6.713c-1.091,0-1.975,0.884-1.975,1.975v11.984c-0.893,0.626-1.481,1.658-1.481,2.83
                        c0,1.906,1.551,3.457,3.457,3.457c0.522,0,1.014-0.125,1.458-0.334l6.87,3.965c0.312,0.181,0.65,0.266,0.986,0.266
                        c0.682,0,1.346-0.354,1.712-0.988c0.545-0.943,0.222-2.152-0.724-2.697l-6.877-3.971c-0.092-1.044-0.635-1.956-1.449-2.526V8.688
                        C23.701,7.598,22.816,6.713,21.726,6.713z M21.726,24.982c-0.817,0-1.481-0.665-1.481-1.48c0-0.816,0.665-1.481,1.481-1.481
                        s1.481,0.665,1.481,1.481C23.207,24.317,22.542,24.982,21.726,24.982z"
                    ></path>
                </svg>
            </div>
            <div
                class="flex justify-start h-8 w-56 md:w-72 -z-10 -mt-6 mb-0 mx-auto lg:mx-0 lg:-ml-7 rounded-2xl bg-main-light"
            ></div>
        </div>
        <div class="self-center">
            <button @click="toggleModal" class="m-2">
                <svg
                    version="1.1"
                    class="h-6 w-6"
                    fill="none"
                    viewBox="0 0 24 24"
                    stroke="currentColor"
                    stroke-width="2"
                >
                    <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        d="M10.325 4.317c.426-1.756 2.924-1.756 3.35 0a1.724 1.724 0 002.573 1.066c1.543-.94 3.31.826 2.37 2.37a1.724 1.724 0 
                        001.065 2.572c1.756.426 1.756 2.924 0 3.35a1.724 1.724 0 00-1.066 2.573c.94 1.543-.826 3.31-2.37 2.37a1.724 1.724 0 
                        00-2.572 1.065c-.426 1.756-2.924 1.756-3.35 0a1.724 1.724 0 00-2.573-1.066c-1.543.94-3.31-.826-2.37-2.37a1.724 1.724 0 
                        00-1.065-2.572c-1.756-.426-1.756-2.924 0-3.35a1.724 1.724 0 001.066-2.573c-.94-1.543.826-3.31 2.37-2.37.996.608 2.296.07 2.572-1.065z"
                    ></path>
                    <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        d="M15 12a3 3 0 11-6 0 3 3 0 016 0z"
                    ></path>
                </svg>
            </button>
        </div>
    </header>
    <AppSettings />
</template>

<script setup>
import { provide, ref } from 'vue';
import AppSettings from '@/components/AppSettings.vue';

const isModalOpen = ref(false);

const toggleModal = () => {
    isModalOpen.value = !isModalOpen.value;
};

provide('isModalOpen', isModalOpen);
</script>
