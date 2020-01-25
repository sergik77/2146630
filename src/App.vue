<template>
<div id="app">
    <div class="row-cols-1 text-left" >
        <div class="col">
            <b-img left src="veronika.png" rounded="circle" alt="Left image" class="mr-2"></b-img>
            <h2>Вероника Ростова</h2>
            <p class="mb-0"><span>Менеджер по продажам</span></p>
            <div class="badgek">
                <p>Подберу для вас самые лучшие предложения.
                    Мои услуги абсолютно бесплатны</p>
            </div>
<div class="services">
    <p class="text-right">Услуг</p>
    <hr>
    <div class="border-left">
        <b-progress :max="max" height="2rem" variant="success">
            <b-progress-bar :value="value1">
                Ручное бронирование
            </b-progress-bar>
            <strong class="ml-auto">{{ value1 }}</strong>
        </b-progress>
        <b-progress :max="max" height="2rem" variant="info">
            <b-progress-bar :value="value2">
                Пакетные туры
            </b-progress-bar>
            <strong class="ml-auto"> {{ value2 }}</strong>
        </b-progress>
        <b-progress :max="max" height="2rem" variant="info">
            <b-progress-bar :value="value3"  aria-valuenow="25" >
                Отели
            </b-progress-bar>
            <strong class="ml-auto">{{ value3 }}</strong>
        </b-progress>
    </div>
    <hr>
    <div class="d-flex">
        <p class="">Всего
        </p>
        <strong class="ml-auto">{{ max }}</strong>

    </div>
</div>
            <div>
                <div class="d-flex grup">
                <img src="../public/heart.svg" class="m-2">
                    <p class="p-1">131</p>
                    <img src="../public/msg.svg" class="m-2">
                    <p class="p-1">14</p>
                </div>
                <b-tabs content-class="mt-3">
                    <b-tab title="Последние отзывы" active> <MassengerList
                            v-bind:messeng ="messeng"
                    />

                    </b-tab>
                    <b-tab title="Все отзывы "> <MassengerList
                            v-bind:messeng ="messeng"
                    />
                    </b-tab>
                </b-tabs>

            </div>
        </div>
    </div>
    <div class="row-cols-1 addmes" >
        <div class="col">
            <AddMasseng
                    v-on:add-masseng="newMasseng"

            />

        </div>
    </div>

  </div>

</template>

<script>

import MassengerList from "./components/MassengerList";
import AddMasseng from "./components/AddMasseng";
export default {
  name: 'app',
  data() {
    return {

        value1: 11,
        value2: 3,
        value3: 1,
        max: 15,
    messeng: [
      {id:1, name: 'Самуил', msg: 'Привет, Верунь! ниче себе ты крутая. фотка класс!!!! ', data: '13 октября 2011'},
      {id:2, name: 'Лилия Семёновна', msg: 'Вероника, здравствуйте! Есть такой вопрос: Особый вид куниц жизненно стабилизирует кинетический момент, это и есть всемирно известный центр огранки алмазов и торговли бриллиантами? ', data: '14 октября 2011'},
      {id:3, name: 'Лилия Семёновна', msg: 'Вероника, здравствуйте! Есть такой вопрос: Особый вид куниц жизненно стабилизирует кинетический момент?', data: '14 октября 2011'}
    ],
        mainProps: { blank: true, width: 75, height: 75, class: 'm1' }
    }
  },
  methods: {
    newMasseng(mess) {
      this.messeng.push(mess)
    }
  },
  components: {
    AddMasseng,
MassengerList
  }
}
</script>

<style lang="scss">
  @import '~bootstrap';
  @import '~bootstrap-vue';
#app {
    margin: 0 auto;
    max-width: 720px;
  font-family: Arial, sans-serif;
    font-size: 14px;
    line-height: 20px ;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 25px;
}
  ul {
      padding-left: 0;
  }
  li {
      list-style: none;
      margin-bottom: 20px;
  }
    h2{
        font-size: 20px;
    }
    h3 {
        font-size: 14px;
        font-weight: bold;
    }
    span {
        font-size: 12px;
    }
.badgek {
    margin-left: 60px;
    background: #fffbc8;
    border: 1px solid #cecabf;
}
    .services {
        margin-left: 130px;
        font-size: 13px;
    }
    .progress {
        /*border-right-radius: 0;*/
        border-top-left-radius: 0;
        border-bottom-left-radius: 0;
        margin: 1px;
        background-color: transparent;

    }
    .progress-bar {
        color: #333;
        font-size: 13px;
        padding-left: 6px;
        text-align: left;
        border-top-right-radius: 2px;
        border-bottom-right-radius: 2px;
        min-width: 30px;
        overflow: visible;
    }
    .bg-success {
        background-color: #b1e19b!important;;
            /*opacity: 0.4;*/
    }
    .bg-info {
        background-color: #ace2f8!important;;
    }
  .nav-tabs .nav-link.active,.nav-tabs .nav-link, .nav-tabs, .nav-tabs .nav-link:focus {
      border: none;
      border-color: transparent;
  }
    .addmes {
        background: #f2f2f2;
    }
    .grup {
        justify-content: flex-end;
        /*text-align: right;*/
        height: 100%;
        margin-bottom: -50px;
    }
    img {
        height: fit-content;
    }
</style>
