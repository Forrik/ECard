<template>
  <div>
  <div v-if="isVisible"  @click="isVisible = !isVisible" class="popup__bgc">
    
  </div>
  <card-modal   @create="createCard"  class="card__popup" v-if="isVisible"/>
    <svg @click="isVisible = !isVisible" class="card__cancel__icon" v-if="isVisible"  fill="#000000" version="1.1" baseProfile="tiny" id="Layer_1" width="30px" height="30px" viewBox="0 0 42 42" xml:space="preserve">
      <path fill-rule="evenodd" d="M21.002,26.588l10.357,10.604c1.039,1.072,1.715,1.083,2.773,0l2.078-2.128  c1.018-1.042,1.087-1.726,0-2.839L25.245,21L36.211,9.775c1.027-1.055,1.047-1.767,0-2.84l-2.078-2.127  c-1.078-1.104-1.744-1.053-2.773,0L21.002,15.412L10.645,4.809c-1.029-1.053-1.695-1.104-2.773,0L5.794,6.936  c-1.048,1.073-1.029,1.785,0,2.84L16.759,21L5.794,32.225c-1.087,1.113-1.029,1.797,0,2.839l2.077,2.128  c1.049,1.083,1.725,1.072,2.773,0L21.002,26.588z"/>
      </svg>
    </div>
  
<div class="container">
  
    <div class="header">
        <input />
        <div class="header__title">Список сотрудников</div>
        <my-button @click="isVisible = !isVisible" >Добавить</my-button>
    </div>
   
    
    <div>
     <card-list :cards="cards" @remove="removeCard" />
    </div>
  
      
 
    
</div>
</template>

<script>
import CardList from './components/CardList.vue';
import CardModal from './components/CardModal.vue'
import MyButton from './components/UI/MyButton.vue';

export default {
  components: {
     CardList, CardModal, MyButton
  },
    data () {
        return {
            cards: [
                {id: 1, lastName:'Маяковский', firstName: 'Владимир', secondName: 'Владимирович',  imgUrl:'https://images11.graziamagazine.ru/upload/img_cache/d51/d51bd08fca58b7464218c2a1ac0836d8_cropped_666x833.webp'},
                {id: 2, lastName:'Достоевский', firstName: 'Фёдор', secondName: 'Михайлович',  imgUrl:'https://upload.wikimedia.org/wikipedia/commons/6/6e/Fyodor_Mikhailovich_Dostoyevsky_1876.jpg'},

            ], 
         isVisible: false
        }
    },
    methods: {
        createCard(card) {
        this.cards.push(card)
        },
        removeCard(card) {
          this.cards = this.cards.filter( c => c.id !== card.id)
        }  
    }
}
</script>

<style>

.popup__bgc {
  background-color: #fff;
  background: rgba(0, 0, 0, .5);
  width: 100%;
  height: 100vh;
  z-index: 2;
  position: absolute;
  top: 0;
  right: 0;
}
.card__popup {

}

.card__cancel__icon {
  position: absolute;
  top: 0;
  right: 0;
  cursor: pointer;
  z-index: 2;
}

body {
    background-color: #f2f7ff;
}
/* Указываем box sizing */
*,
*::before,
*::after {
  box-sizing: border-box;
}

body::-webkit-scrollbar {
  width: 0;
}

/* Убираем внутренние отступы */
ul[class],
ol[class] {
  padding: 0;
}

/* Убираем внешние отступы */
body,
h1,
h2,
h3,
h4,
p,
ul[class],
ol[class],
li,
figure,
figcaption,
blockquote,
dl,
dd {
  margin: 0;
}

/* Выставляем основные настройки по-умолчанию для body */
body {
  min-height: 100vh;
  scroll-behavior: smooth;
  text-rendering: optimizeSpeed;
  line-height: 1.5;
}

/* Удаляем стандартную стилизацию для всех ul и il, у которых есть атрибут class*/
ul[class],
ol[class] {
  list-style: none;
}

/* Элементы a, у которых нет класса, сбрасываем до дефолтных стилей */
a:not([class]) {
  text-decoration-skip-ink: auto;
}

/* Упрощаем работу с изображениями */
img {
  max-width: 100%;
  display: block;
}

/* Указываем понятную периодичность в потоке данных у article*/
article > * + * {
  margin-top: 1em;
}

/* Наследуем шрифты для инпутов и кнопок */
input,
button,
textarea,
select {
  font: inherit;
}

/* Удаляем все анимации и переходы для людей, которые предпочитай их не использовать */
@media (prefers-reduced-motion: reduce) {
  * {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
.container {
    width: 1280px;
    margin: 50px auto;
   background-color: rgba(157, 209, 255, 0.35);
   padding: 30px;
   border-radius: 20px;
   z-index: 1;
   position: relative;
}

.header {
 display: flex;
 justify-content: space-between;

}



</style>