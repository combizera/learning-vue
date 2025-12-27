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
