<template>

    <Head title="Demo1" meta="abc" />
    <div class="bg-white h-screen text-sm">

        <nav
            class=" bg-white sticky top-0 z-10 flex justify-between items-center px-1 lg:px-2 h-14  lg:w-2/3 lg:mx-auto">
            <!-- logo -->
            <div class="pr-4">
                <ApplicationLogo class="block h-9 w-auto" />
            </div>
            <!-- button burger -->
            <!-- <div class="lg:hidden w-full flex justify-start">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"
                    class=" h-5 fill-slate-700 hover:fill-slate-400 cursor-pointer">
                    <path
                        d="M0 96C0 78.33 14.33 64 32 64H416C433.7 64 448 78.33 448 96C448 113.7 433.7 128 416 128H32C14.33 128 0 113.7 0 96zM0 256C0 238.3 14.33 224 32 224H416C433.7 224 448 238.3 448 256C448 273.7 433.7 288 416 288H32C14.33 288 0 273.7 0 256zM416 448H32C14.33 448 0 433.7 0 416C0 398.3 14.33 384 32 384H416C433.7 384 448 398.3 448 416C448 433.7 433.7 448 416 448z" />
                </svg>
            </div> -->
            <!-- menu link -->
            <div class="hidden lg:block w-full">
                <div class="flex lg:space-x-10">
                    <Link
                        class=" border-b-2 border-blue-700  hover:bg-blue-200 p-2 hover:border-green-400 hover:border-b-2">
                    Menu 1
                    </Link>
                    <Link class=" hover:bg-blue-200 p-2 hover:border-green-400 hover:border-b-2"> Menu 2 </Link>
                    <Link class=" hover:bg-blue-200 p-2 hover:border-green-400 hover:border-b-2"> Menu 3 </Link>
                    <Link class=" hover:bg-blue-200 p-2 hover:border-green-400 hover:border-b-2"> Menu 4 </Link>
                    <Link
                        class="inline-flex items-center hover:bg-blue-200 p-2 hover:border-green-400 hover:border-b-2">
                    Menu 5
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512" class=" ml-2 h-3">
                        <path
                            d="M224 416c-8.188 0-16.38-3.125-22.62-9.375l-192-192c-12.5-12.5-12.5-32.75 0-45.25s32.75-12.5 45.25 0L224 338.8l169.4-169.4c12.5-12.5 32.75-12.5 45.25 0s12.5 32.75 0 45.25l-192 192C240.4 412.9 232.2 416 224 416z" />
                    </svg>
                    </Link>
                </div>
            </div>
            <!-- rightside -->
            <div class=" lg:w-1/3 inline-flex justify-end font-bold underline">
                <!-- button burger -->
                <div class="lg:hidden w-full flex justify-start mr-2 p-2 rounded-md text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:bg-gray-100 focus:text-gray-500 transition duration-150 ease-in-out"
                    @click.prevent="toggleMenu = !toggleMenu">
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"
                        class=" h-5 fill-slate-700 hover:fill-slate-400 cursor-pointer">
                        <path
                            d="M0 96C0 78.33 14.33 64 32 64H416C433.7 64 448 78.33 448 96C448 113.7 433.7 128 416 128H32C14.33 128 0 113.7 0 96zM0 256C0 238.3 14.33 224 32 224H416C433.7 224 448 238.3 448 256C448 273.7 433.7 288 416 288H32C14.33 288 0 273.7 0 256zM416 448H32C14.33 448 0 433.7 0 416C0 398.3 14.33 384 32 384H416C433.7 384 448 398.3 448 416C448 433.7 433.7 448 416 448z" />
                    </svg>
                </div>
                <Link :href="route('login')"
                    class="hidden lg:inline-flex  items-center py-2 px-6 border border-blue-500 rounded-full hover:bg-blue-200">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512" class="pr-2 h-3">
                    <path
                        d="M80 192V144C80 64.47 144.5 0 224 0C303.5 0 368 64.47 368 144V192H384C419.3 192 448 220.7 448 256V448C448 483.3 419.3 512 384 512H64C28.65 512 0 483.3 0 448V256C0 220.7 28.65 192 64 192H80zM144 192H304V144C304 99.82 268.2 64 224 64C179.8 64 144 99.82 144 144V192z" />
                </svg>
                Login
                </Link>
            </div>
            <!-- responsive menu -->
            <div v-if="toggleMenu"
                class=" bg-white flex flex-col gap-4 absolute left-0 right-0 top-14 shadow-xl z-100 py-2">
                <Link class=" px-2 py-2 hover:bg-slate-200">Menu 1</Link>
                <Link class=" px-2 py-1 hover:bg-slate-200">Menu 1</Link>
                <Link class=" px-2 py-1 hover:bg-slate-200">Menu 1</Link>
                <Link class=" px-2 py-1 hover:bg-slate-200">Menu 1</Link>
                <Link
                    class="inline-flex justify-between items-center hover:bg-blue-200 p-2 hover:border-green-400 hover:border-b-2">
                Menu 5
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512" class=" ml-2 h-3">
                    <path
                        d="M224 416c-8.188 0-16.38-3.125-22.62-9.375l-192-192c-12.5-12.5-12.5-32.75 0-45.25s32.75-12.5 45.25 0L224 338.8l169.4-169.4c12.5-12.5 32.75-12.5 45.25 0s12.5 32.75 0 45.25l-192 192C240.4 412.9 232.2 416 224 416z" />
                </svg>
                </Link>
                <hr />
                <Link :href="route('login')" class="inline-flex  items-center px-2 py-1 hover:bg-slate-200">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512" class="pr-2 h-3">
                    <path
                        d="M80 192V144C80 64.47 144.5 0 224 0C303.5 0 368 64.47 368 144V192H384C419.3 192 448 220.7 448 256V448C448 483.3 419.3 512 384 512H64C28.65 512 0 483.3 0 448V256C0 220.7 28.65 192 64 192H80zM144 192H304V144C304 99.82 268.2 64 224 64C179.8 64 144 99.82 144 144V192z" />
                </svg>
                Login
                </Link>
            </div>
        </nav>
        <div class="flex flex-col  px-1 lg:px-2 h-14  lg:w-2/3 lg:mx-auto  py-2">
            <div class=" h-48">main content</div>
        </div>

    </div>
</template>
<script setup>
import { computed, onMounted, onUnmounted, ref } from 'vue';
import { Head, Link } from '@inertiajs/inertia-vue3';
import ApplicationLogo from '@/Components/ApplicationLogo.vue';

defineProps({
    canLogin: Boolean,
    canRegister: Boolean,
    laravelVersion: String,
    phpVersion: String,
})

onMounted(window.onresize = () => {
    toggleMenu.value = false
});
const toggleMenu = ref(false)
</script>
