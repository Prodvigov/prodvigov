<template>
	<b-table :fields="fields" :items="items" outlined responsive>
      <template #cell(id)="id">
        <a :href="id.value" class="text-break">{{ id.value }}</a>
      </template>
       <template #cell(review)="review">
        <a :href="review.value">{{ review.value }}</a>
      </template>
    </b-table>
</template>

<script>
export default {
    data() {
      return {

        fields: [       
          {
            key: 'title',
            label: 'Запросы'
            
          },
          {
            key: 'id',
            label: 'Ссылки'
          
          },
          {
            key: 'userId',
            label: 'Яндекс'

          },
          {
            key: 'review',
            label: 'Анализ'

          }
        ],
        items: [
          { id: 'http://giftsfactory.ru/', title: 'Корпоративные подарки', userId: 1, review: 'показать', 
         _cellVariants: { userId: 'center text-center' }},
          { id: 'https://giftsfactory.ru/novogodnie_podarki/', title: 'Корпоративные подарки на новый год', userId: 2, review: 'показать', 
         _cellVariants: { userId: 'center text-center' }},
          { id: 'http://giftsfactory.ru/', title: 'Корпоративные подарки купить', userId: 3, review: 'показать',
         _cellVariants: { userId: 'center text-center' }}
        ]

 }
	},
    mounted() {
      fetch('https://jsonplaceholder.typicode.com/todos/?_limit=6')
  .then(response => response.json())
  .then(json => {this.items = json})
    }
}
</script>