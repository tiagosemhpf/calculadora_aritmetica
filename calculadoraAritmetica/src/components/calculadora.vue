<template>
    <div>
        <h2>Calculadora Aritmética</h2>
        <input type="number" v-model.number="num1" placeholder="Digite o primeiro número" />
        <input type="number" v-model.number="num2" placeholder="Digite o segundo número" />

        <select v-model="operacao">
            <option value="+">+</option>
            <option value="-">-</option>
            <option value="*">*</option>
            <option value="/">/</option>
        </select>

        <p>Resultado: {{ resultado }}</p>
    </div>
</template>

<script>
export default {
    data() {
        return {
            num1: 0,
            num2: 0,
            operacao: '+'
        };
    },
    computed: {
        resultado() {
            switch (this.operacao) {
                case '+':
                    return this.num1 + this.num2;
                case '-':
                    return this.num1 - this.num2;
                case '*':
                    return this.num1 * this.num2;
                case '/':
                    return this.num2 !== 0 ? this.num1 / this.num2 : 'Erro: Divisão por zero';
                default:
                    return 0;
            }
        }
    }
};
</script>

<style scoped>
input,
select {
    margin: 10px 5px;
    padding: 5px;
    font-size: 16px;
}
</style>