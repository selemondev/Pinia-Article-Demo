<script setup>
import Pinia_Logo from "../assets/svg/Pinia.svg";
import { ShoppingCartIcon } from '@heroicons/vue/24/solid';
import { useProductStore } from "../stores/productStore";
const productStore = useProductStore();
</script>
<template>
    <div>
        <header>
            <nav class="w-full h-14 flex-between p-2 bg-[#eee]">
                <div class="flex-center space-x-1">
                    <img :src="Pinia_Logo" alt="Pinia" class="w-10 h-10">
                    <h1 class="font-bold text-base md:text-2xl">
                        <router-link to="/">Store</router-link>
                    </h1>
                </div>


                <div>
                    <router-link to="/cart">
                        <div class="w-5.5 h-5.2 rounded-full ml-1 text-center bg-red-500 md:w-6 md:h-6">
                            <span class="text-white text-sm">{{ productStore.cartQuantity }}</span>
                        </div>
                        <ShoppingCartIcon class="w-6 h-6 md:w-8 md:h-8" />
                    </router-link>
                </div>
            </nav>
        </header>
    </div>
</template>