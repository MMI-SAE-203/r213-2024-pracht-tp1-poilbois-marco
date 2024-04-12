<script setup lang="ts">
    import { ref } from 'vue'

    const sectionOpen = ref(1);
</script>

<template>
    <section>
        <button>
            <span class="text-xl" @pointerdown="sectionOpen = 1">bouton 1</span>
            <p v-show="sectionOpen === 1">Lorem ipsum dolor sit amet consectetur adipisicing elit. Tempore mollitia iure ipsam assumenda quaerat optio laborum, minima aliquid ducimus autem excepturi labore sit vel adipisci! Placeat, tempora? Vero, reiciendis consectetur.</p>
        </button>
    </section>
    <section>
        <button>
            <span class="text-xl" @pointerdown="sectionOpen = 2">bouton 2</span>
            <p v-show="sectionOpen === 2">Quam repellat, necessitatibus culpa quod adipisci voluptas earum minima sed enim, tenetur fugit alias! Tempore iure vero illo, cupiditate ipsam libero atque quas. Sed, laborum rem quasi doloremque impedit maiores?</p>
        </button>
    </section>
    <section>
        <button>
            <span class="text-xl" @pointerdown="sectionOpen = 3">bouton 3</span>
            <p v-show="sectionOpen === 3">Culpa aperiam iure sed soluta. Tenetur eos dolorum perspiciatis cupiditate voluptas autem iusto unde officia in, ducimus voluptates magni magnam, consequuntur nostrum voluptatibus debitis perferendis nesciunt sit ad quos nulla.</p>
        </button>
    </section>
</template>
