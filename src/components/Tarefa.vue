<template>
    <Box>
        <div class="columns">
            <div class="column is-7">
                {{ nomeTarefa.descricao || "Tarefa sem descrição"}}
            </div>
            <div class="column">
                <Cronometro :tempoEmSegundos="nomeTarefa.duracaoEmSegundos"></Cronometro>
            </div>
        </div>
    </Box>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';
import Cronometro from './Cronometro.vue';
import Box from './Box.vue';
import ITarefa from '@/interfaces/ITarefa';

export default defineComponent({
    name: "TarefaVue",
    props: {
        nomeTarefa: {
            type: Object as PropType<ITarefa>,
            required: true
        }
    },
    components: {
        Cronometro,
        Box
    }
})
</script>
