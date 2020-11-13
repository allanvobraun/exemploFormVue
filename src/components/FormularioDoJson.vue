<template>


  <b-card title="Titulo do card" header-tag="header" footer-tag="footer">
    <template #header>
      <h6 class="mb-0">Header aqui</h6>
    </template>
    <b-card-body>
      <b-form @submit.prevent="submeter">

        <b-form-group
            id="input-group-1"
            label="Endereço de email:"
            label-for="input-1"
        >
          <b-form-input
              id="input-1"
              type="email"
              v-model="formJson.email"
              required
              placeholder="Digite seu email"
          ></b-form-input>
        </b-form-group>

        <b-form-group id="input-group-2" label="Seu nome:" label-for="input-2">
          <b-form-input
              id="input-2"
              v-model="formJson.nome"
              required
              placeholder="Digite seu nome"
          ></b-form-input>
        </b-form-group>

        <b-button type="submit" variant="primary">Submit</b-button>
      </b-form>
    </b-card-body>

  </b-card>

</template>

<script>
export default {
  name: 'FormularioDoJson',
  data() {
    return {
      formJson: {
        email: '',
        nome: '',
      }
    }
  },
  methods: {
    submeter() {
      console.log(this.formJson);
      this.download('seilaoq.json', JSON.stringify(this.formJson))
    },
    download(filename, text) {
      const element = document.createElement('a');
      element.setAttribute('href', 'data:text/plain;charset=utf-8,' + encodeURIComponent(text));
      element.setAttribute('download', filename);

      element.style.display = 'none';
      document.body.appendChild(element);

      element.click();

      document.body.removeChild(element);
    }
  }
}
</script>