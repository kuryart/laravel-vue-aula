<template>
    <div class="relative flex min-h-screen">
        <!-- Sidebar -->
        <div class="bg-test flex flex-col shadow-[0px_0px_16px_8px_rgba(0,0,0,0.25)]" :class="[ isCollapsed ? 'w-24' : 'w-48']">
            <!-- Drawer -->
            <div class="flex flex-row justify-end pt-5 pr-3">
                <n-icon @click="toggle" size="24" color="white" class="hover:cursor-pointer" :class="{ clicked: !isCollapsed }">
                    <arrow-forward-ios-round />
                </n-icon>
            </div>
            <!-- Avatar -->
            <div class="flex flex-row justify-center pt-10">
                <div class="flex flex-col items-center">
                    <n-avatar
                        round
                        :size="64"
                        src="https://07akioni.oss-cn-beijing.aliyuncs.com/07akioni.jpeg"
                    />
                    <h3 class="text-white pt-2 text-center">Nome do Fulano</h3>
                </div>
            </div>
            <!-- Menu -->
            <div class="flex flex-col pt-20 gap-y-3">
                <div class="w-full h-12 flex flex-row justify-center">
                    <div class="flex flex-col justify-center">
                        <n-icon v-if="isCollapsed" size="30" color="white" >
                            <clipboard-regular class="hover:text-[#2FD67B]" />
                        </n-icon>
                        <h2 v-else class="text-white pt-2 text-center">Cadastro</h2>
                    </div>
                </div>
                <div class="w-full h-12 flex flex-row justify-center hover:bg-[#2FD67B]">
                    <div class="flex flex-col justify-center">
                        <n-icon v-if="isCollapsed" size="30" color="white">
                            <exchange-alt />
                        </n-icon>
                        <h2 v-else class="text-white pt-2 text-center">Comercial</h2>
                    </div>
                </div>
                <div class="w-full h-12 flex flex-row justify-center hover:bg-[#2FD67B]">
                    <div class="flex flex-col justify-center">
                        <n-icon v-if="isCollapsed" size="30" color="white">
                            <attach-money-round />
                        </n-icon>
                        <h2 v-else class="text-white pt-2 text-center">Financeiro</h2>
                    </div>
                </div>
                <div class="w-full h-12 flex flex-row justify-center hover:bg-[#2FD67B]">
                    <div class="flex flex-col justify-center">
                        <n-icon v-if="isCollapsed" size="30" color="white">
                            <users />
                        </n-icon>
                        <h2 v-else class="text-white pt-2 text-center">Convênio</h2>
                    </div>
                </div>
                <div class="w-full h-12 flex flex-row justify-center hover:bg-[#2FD67B]">
                    <div class="flex flex-col justify-center">
                        <n-icon v-if="isCollapsed" size="30" color="white">
                            <settings-sharp />
                        </n-icon>
                        <h2 v-else class="text-white pt-2 text-center">Parametrização</h2>
                    </div>
                </div>
            </div>
        </div>
        <!-- Main content -->
        <div class="flex-1">
            <div class="px-2 py-4">Header</div>
            <div class="p-8">Content</div>
        </div>
    </div>
</template>

<script>
import { ExchangeAlt, ClipboardRegular, Users } from "@vicons/fa";
import {
    ArrowForwardIosRound,
    AttachMoneyRound,
    SettingsSharp,
} from "@vicons/material";
import { NIcon, NAvatar } from "naive-ui";

export default {
    data() {
        return {
            isCollapsed: true,
        }
    },
    components: {
        ExchangeAlt,
        ClipboardRegular,
        ArrowForwardIosRound,
        AttachMoneyRound,
        Users,
        SettingsSharp,
        NIcon,
        NAvatar,
    },
    methods: {
        toggle() {
            console.log('teste');
            this.isCollapsed = !this.isCollapsed;
        }
    }
};
</script>

<style>

.clicked {
  transform: rotate(180deg);
}



</style>
