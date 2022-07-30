<script setup>
import { ref, onMounted } from 'vue';
import { Link } from '@inertiajs/inertia-vue3';
import BreezeApplicationLogo from '@/Components/ApplicationLogo.vue';
import SidebarMenu from '@/Components/SidebarLink.vue';
import BreezeDropdown from '@/Components/Dropdown.vue';
import BreezeDropdownLink from '@/Components/DropdownLink.vue';
onMounted(window.onresize = () => {
    showSidebar.value = false
});
const showSidebar = ref(false);
</script>

<template>
    <div class="flex h-screen bg-white text-sm">
        <!-- sidebar -->
        <div class=" w-64  bg-slate-800 text-white absolute inset-y-0 left-0 lg:relative lg:-translate-x-0 transform -translate-x-full transition duration-200 ease-in-out "
            :class="{'relative -translate-x-0':showSidebar}">
            <!-- logo -->
            <div class=" h-14 flex justify-start items-center  text-indigo-500 px-3">
                <Link :href="route('dashboard')">
                <BreezeApplicationLogo class="block h-9 w-auto fill-indigo-500" />
                </Link>
                <span class=" text-2xl capitalize">logos</span>
            </div>
            <div class="w-full border-t mb-2 border-gray-300"></div>
            <!-- main menu -->
            <div
                class=" h-full flex flex-col gap-2 scrollbar-thin scrollbar-thumb-slate-700 scrollbar-track-slate-300 overflow-y-scroll scrollbar-thumb-rounded-full scrollbar-track-rounded-full">
                <SidebarMenu :href="route('dashboard')">
                    <font-awesome-icon icon="house" class="h-5" />
                    Menu 1
                </SidebarMenu>
            </div>
        </div>
        <!-- main -->
        <div class=" flex-1 w-full scrollbar-thin scrollbar-thumb-slate-300">
            <!-- topbar -->
            <div class="px-3 mb-2 h-14 flex justify-between items-center w-full gap-2 shadow-md">
                <div>
                    <div class="-mr-2 flex items-center lg:hidden">
                        <button @click="showSidebar = ! showSidebar"
                            class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:bg-gray-100 focus:text-gray-500 transition duration-150 ease-in-out">
                            <svg class="h-6 w-6" stroke="currentColor" fill="none" viewBox="0 0 24 24">
                                <path :class="{'hidden': showSidebar, 'inline-flex': ! showSidebar }"
                                    stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M4 6h16M4 12h16M4 18h16" />
                                <path :class="{'hidden': ! showSidebar, 'inline-flex': showSidebar }"
                                    stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M6 18L18 6M6 6l12 12" />
                            </svg>
                        </button>
                    </div>
                </div>
                <div class="inline-flex gap-2">
                    <div>
                        <font-awesome-icon icon="bell" class=" h-4 p-3 rounded-full cursor-pointer bg-slate-200 " />
                    </div>
                    <div>
                        <font-awesome-icon icon="gear" class=" h-4 p-3 rounded-full cursor-pointer bg-slate-200 " />
                    </div>
                    <div>
                        <BreezeDropdown >
                            <template #trigger>
                                <font-awesome-icon icon="caret-down"
                                    class=" h-4 p-3 rounded-full cursor-pointer bg-slate-200 " />
                            </template>
                            <template #content>
                                <BreezeDropdownLink :href="route('logout')" method="post" as="button">
                                    Log Out
                                </BreezeDropdownLink>
                            </template>
                        </BreezeDropdown>
                    </div>
                </div>
            </div>
            <!-- main section -->
            <div>
                <slot />
            </div>
        </div>
    </div>
</template>
