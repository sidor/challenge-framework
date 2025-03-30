<template>
    <div class="text-center">
        <h2>Congratulations, you have solved this challenge!</h2>
        <p class="my-2">
            Share your success and motivate your friends to give it a try!
        </p>
        <div>
            <ShareNetwork
                v-for="network in socialNetworks"
                :key="network.name"
                :network="network.name"
                url="https://challenge.bellingcat.com/"
                v-slot="{ share }"
            >
                <v-btn
                    variant="flat"
                    color="primary"
                    @click="share"
                    class="text-capitalize mt-2 mx-2 px-3"
                >
                    <v-icon :size="16" class="mr-1">
                        {{ network.icon }}
                    </v-icon>
                    {{ network.label }}
                </v-btn>
            </ShareNetwork>
        </div>
    </div>
</template>

<script setup>
import { defineProps } from "vue";
import { ShareNetwork } from "vue3-social-sharing";
import socialNetworks from "@/data/social";

defineProps({
    puzzle: Object,
});
</script>
