
<div class="row mb-5 mt-5">

<b-table :items="items2" :fields="fields2" responsive>
  
  <template #cell(show_details)="row">
        
    <b-button size="sm" @click="row.toggleDetails" class="mr-2">
      {{ row.detailsShowing ? 'Скрыть' : 'Показать'}} 
    </b-button>

  </template>

  <template #row-details="row">
        
    <b-card>
      <b-row class="mb-2">
        <b-col sm="3" class="text-sm-right"><b>{{ row.item.isActive }}</b></b-col>
        <b-col>{{ row.item.age }}</b-col>
      </b-row>
    </b-card>
  </template>

</b-table>
     

</div>
<script>

export default {
 
  components: {
 
},
    data() {
      return {
          fields2: ['first_name', 'last_name', 'show_details'],
        items2: [
          { isActive: true, age: 40, first_name: 'Dickerson', last_name: 'Macdonald' },
          { isActive: false, age: 21, first_name: 'Larsen', last_name: 'Shaw' },
          {
            isActive: false,
            age: 89,
            first_name: 'Geneva',
            last_name: 'Wilson',
            _showDetails: true
          },
          { isActive: true, age: 38, first_name: 'Jami', last_name: 'Carney' }
        ]
      }
    }
  }
</script>