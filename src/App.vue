<template>
    <div class="container">
        <div id="app" class="p-5 mb-4 mt-4 bg-light rounded-3">
            <h1>Calculadora Aritmética</h1>
            <div>
                <input v-model.number="numero1" placeholder="Primeiro Número" type="number" />
                <select v-model="operacao">
                    <option value="add">+</option>
                    <option value="subtract">-</option>
                    <option value="multiply">*</option>
                    <option value="divide">/</option>
                </select>
                <input v-model.number="numero2" placeholder="Segundo Número" type="number" />
            </div>
            <h2>Resultado: {{ resultado }}</h2>
        </div>
    </div>

</template>

<script>
export default {
    data() {
        return {
            numero1: 0,
            numero2: 0,
            operacao: 'add'
        }
    },
    computed: {
        resultado() {
            switch (this.operacao) {
                case 'add':
                    return this.numero1 + this.numero2;
                case 'subtract':
                    return this.numero1 - this.numero2;
                case 'multiply':
                    return this.numero1 * this.numero2;
                case 'divide':
                    return this.numero2 !== 0 ? this.numero1 / this.numero2 : 'Erro: Divisão por zero';
                default:
                    return 0;
            }
        }
    }
}
</script>

<style>
#app {
    text-align: center;
    max-width: 400px;
    margin: 0 auto;
    padding-top: 50px;
}

input,
select {
    margin: 20px 0;
    padding: 10git branchpx;
    width: 100%;
    box-sizing: border-box;
}

h2 {
    margin-top: 30px;
    font-size: 54px;
}
</style>
