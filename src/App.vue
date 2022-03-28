<template>
  <div class="container mt-4">
    <div class="row">
      <div class="col-sm-6 mx-auto">
    <form @submit.prevent="registerUser" >
      

  <div v-show="step === 0" class="step">

  <div class="from-group">
    <label for="Fam" class="form-label">Фамилия</label>
    <input type="text" class="form-control" id="Fam" required>
      </div>

  <div class="mb-3">
    
    <label for="name" class="form-label">Имя</label>
    <input type="text" class="form-control" id="name" required>
    
  </div>

  <div class="mb-3">
    <label for="nameFather" class="form-label">Отчество</label>
    <input type="text" class="form-control" id="nameFather">
    
  </div>

  <div class="mb-3">
    <label for="birthday" class="form-label">Дата рождения</label>
    <input type="data" class="form-control" id="birthday" required>
  </div>

  <div class="mb-3">
    <label for="phone" class="form-label">Номер телефона</label>
    <p><input type="text" v-on:keypress="NumbersOnly" required></p>
   
  </div>

  <span>Пол: {{ selected }}</span>
  <select v-model="selected">
  <option disabled value="">Значения</option>
  <option>Мужской</option>
  <option>Женский</option>
  <option>Неопределенный</option>
</select>
<div class="mt-1">
<span>Группа клиентов: {{ selected }}</span>
  <select multiple size="3">
    <option>VIP</option>
    <option>Проблемные</option>
    <option>ОМС</option>    
  </select>
</div>
<div>
<span>Лечащий врач: {{ selected }}</span>
  <select v-model="selected">
  <option disabled value="">Значения</option>
  <option>Иванов</option>
  <option>Захаров</option>
  <option>Чернышева</option>
</select>
</div>
  
  <div class="from-group form-check">
    <input type="checkbox" class="form-check-input" id="exampleCheck1">
    <label class="form-check-label" for="exampleCheck1">Не отправлять смс</label>
  </div>
  <p><input type="submit" value="Проверить данные"></p>
  <form class="form" v-on:submit.prevent>
    
    <button @click="nextStep" type="bytton" class="btn btn-primary">Следующий шаг</button>    
</form>
  </div>



<div v-show="step === 1" class="step">

  <div class="from-group">
    <label for="Index" class="form-label">Индекс</label>
    <input type="number" class="form-control" id="Index" >
      </div>

  <div class="mb-3">
    <label for="Countre" class="form-label">Страна</label>
    <input type="text" class="form-control" id="Countre">
  </div>

  <div class="mb-3">
    <label for="Obl" class="form-label">Область</label>
    <input type="text" class="form-control" id="Obl">
  </div>

  <div class="mb-3">
    <label for="City" class="form-label">Город</label>
    <input type="text" class="form-control" id="City" required>
  </div>

  <div class="mb-3">
    <label for="Yl" class="form-label">Улица</label>
    <input type="text" class="form-control" id="Yl">
  </div>

  <div class="mb-3">
    <label for="House" class="form-label">Дом</label>
    <input type="text" class="form-control" id="House">
  </div>

  

  
  
  <p><input type="submit" value="Проверить данные"></p>
  
  <form class="form" v-on:submit.prevent>
    <button @click="nextStep" type="bytton" class="btn btn-primary">Следующий шаг</button>
    <button @click="backStep" type="bytton" class="btn btn-secondary mt-1" >Предыдущий шаг</button>    
</form>
  
  </div>

<div v-show="step === 2" class="step">

  <span>Тип документов: {{ selected }}</span>
  <select v-model="selected">
  <option disabled value="">Значения</option>
  <option>Паспорт</option>
  <option>Свидетельство о рождении</option>
  <option>Вод. удостоверение</option>
</select>

  <div class="mb-3">
    <label for="namePass" class="form-label">Серия</label>
    <input type="number" class="form-control" id="namePass">
  </div>

  <div class="mb-3">
    <label for="nomber" class="form-label">Номер</label>
    <input type="number" class="form-control" id="nomber">
  </div>

  <div class="mb-3">
    <label for="KtoDal" class="form-label">Кем выдан</label>
    <input type="text" class="form-control" id="KtoDal">
  </div>

  <div class="mb-3">
    <label for="dataV" class="form-label">Дата выдачи</label>
    <input type="date" class="form-control" id="dataV" required>
  </div>

  
  
 <p><input type="submit" value="Проверить данные"></p>
  <form class="form" v-on:submit.prevent>
    <button @click="backStep" type="bytton" class="btn btn-secondary">Предыдущий шаг</button> 
    <button @click="registerUser" type="submit" class="btn btn-success mt-1">Зарегистрировать</button>   
</form>
  </div>
  

</form>
</div>
    </div>
</div>
  
</template>

<script>


export default {
  data(){
    return{
      step:0 
    }
    
  },
  
  

methods: {
  nextStep(){
    
    this.step++, 
     console.info  
  },  
  backStep(){
    this.step--    
  },
  registerUser(){
    if (this.name.innerText === ''){
alert("Регистрация прошла успешно")
    }
    
  }  
},
  checkForm: function () {
      if (this.name ) {
        return true;
      }

      this.errors = [];

      if (!this.name) {
        this.errors.push('Требуется указать имя.');
      }
     

  }
  }
  
</script>


<style>

</style>
