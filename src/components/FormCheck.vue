<template>
<div>
	<b-card class="mt-3" header="Проверка позиций">
<b-form @submit="onSubmit" v-if="show">
        <b-form-input class="mb-3"
          id="input-1"
          v-model="form.url"
          type="url"
          required
          placeholder="Введите URL адрес сайта:"
        ></b-form-input>
    

       <b-form-select class="mb-3"
          id="input-3"
          v-model="form.region"
          :options="regions"
          required

        ></b-form-select>

         
        <b-form-textarea class="mb-3"
    id="textarea"
    v-model="form.textarea"
    required
    placeholder="Введите запросы (до 100шт.), каждый с новой строки..."
    rows="5"
  ></b-form-textarea>
      

      <b-form-group id="input-group-4">
        <b-form-checkbox-group v-model="form.checked" id="checkboxes-4">
          <b-form-checkbox value="me">Яндекс</b-form-checkbox>
          <b-form-checkbox value="that">Google</b-form-checkbox>
        </b-form-checkbox-group>
      </b-form-group>

      <b-button type="submit" variant="primary">Проверить</b-button>
    
    </b-form>

 </b-card>
	</div>
</template>

<script>
export default {
    data() {
      return {
        form: {
          url: '',
          textarea: '',
          region: null,
          checked: []
        },
        regions: [{ text: 'Выберите регион', value: null }, 'Москва', 'Питер', 'Самара', 'Хабаровск'],
        show: true
     
      }
    },
    methods: {
      onSubmit(evt) {
        evt.preventDefault()
        alert(JSON.stringify(this.form))
      },
      
    }
  }
</script>