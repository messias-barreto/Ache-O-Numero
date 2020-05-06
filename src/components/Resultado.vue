<template>
    <div class="card horizontal">      
        <div class="card-stacked">
            <div class="card-content">
                <h5>Resultado</h5>
                <p>Tentativas: {{ n_tentativa }} de 10</p>
                <hr>
                <h5>{{ m_ensagem }}</h5>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: ["m_ensagem","n_tentativa"],
    }
</script>

<style scoped>
    
</style> 