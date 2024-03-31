<script setup>

    import useClima from '../composables/useClima';

    const { formaterTemperatura } = useClima();
    defineProps({
        clima: {
            type: Object,
            default: true
        },
    })

</script>

<template>

    <div class="resultado">
        <h2>Clima de: {{ clima.name }}</h2>
        <p class="actual">{{ formaterTemperatura (clima.main.temp) }}&deg;C</p>
        
        <div class="temperaturas">
            <p>Min: <span>{{ formaterTemperatura (clima.main.temp_min) }}&deg;C</span></p>
            <p>Min: <span>{{ formaterTemperatura (clima.main.temp_max) }}&deg;C</span></p>
        </div>
    </div>

</template>