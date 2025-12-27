# Fundamentos de Vue.js

No Vue, a gente no mesmo arquivo, cria o html/css/js.

Exemplo:

```vue
<script>
export default {
  data() {
    return {
      mensagem: "Olá, Vue!",
    };
  },
};
</script>

<template>
  <div class="app">
    <h1>{{ mensagem }}</h1>
  </div>
</template>

<style>
.app {
  text-align: center;
}
</style>
```

Aí estamos criando o componente e passando uma variável mensagem, que é exibida no template.

### CSS Scoped

Também podemos passar lá no `<style>` o atributo `scoped`, que faz com que o estilo seja aplicado apenas ao componente atual.

```vue
<style scoped>
.app {
  text-align: center;
}
</style>
```

Dessa forma, o estilo `.app` não vai interferir em outros componentes que também tenham uma classe `.app`.

### Watchers

Watchers são usados para observar mudanças em dados reativos e executar uma função quando esses dados mudam.
Eles são úteis quando você quer reagir a mudanças específicas em dados, como fazer uma chamada de API quando um valor muda.

```vue
<script>
export default {
  data() {
    return {
      count: 0,
    };
  },
  watch: {
    count(newValue, oldValue) {
      console.log(`Count mudou de ${oldValue} para ${newValue}`);
      // Aqui você pode adicionar lógica adicional que deve ocorrer quando 'count' muda
    },
  },
};
</script>
```
