<template>
  <div id="filter">
    <div class="f-title">Filt produktów</div>


    <div class="category-box">
      <b class="category">Typ produktu</b><br>
      <select class="select">
        <option>test</option>
        <option>test2</option>
      </select>

    </div>


    <div class="price">
      <b class="category">Ustawienia ceny</b><br>
      <input type="number" v-model="priceMin" id="price-min">
      <span>-</span>
      <input type="number" v-model="priceMax" id="price-max">
    </div>
    <div class="makers">
      <b class="category">Marka produktu</b><br>

      <div class="pretty p-default" v-for="maker in makers">
        <input type="checkbox" :value="maker.name" v-model='makerCheck'>
        <div class="state">
          <label>
            {{maker.name}}
            <span class='maker-count'>({{maker.count}})</span>
          </label>
        </div>
      </div>

    </div>

    <div class="condition">
      <b class="category">Stan produktu</b><br>

      <div class="pretty p-default" v-for="item in conditionOptions">
        <input type="checkbox" :value="item.status" v-model='conditionCheck'>
        <div class="state">
          <label>
            {{item.status}}
          </label>
        </div>
      </div>

    </div>

  </div>
</template>

<script>
export default {
  name: "Filter",
  data() {
    return {
      makers: [
        {id:1,name:"Aoc",count:15},
        {id:1,name:"Apple",count:12},
        {id:1,name:"Samsung",count:1},
        {id:1,name:"Lenovo",count:5},
        {id:1,name:"Huawei",count:7},
        {id:1,name:"Asus",count:8},
      ],
      conditionOptions: [
        {status : "Nowy",},
        {status : "Lekko Używany",},
        {status : "Używany",},
      ],
      conditionCheck: [],
      makerCheck : [],
      priceMin : 0,
      priceMax : 9000,
    }
  },

}
</script>

<style>

.select {
  width: 100%;
  height: 30px;
  text-align: center;
  background: transparent;
  color: #cccccc;
  font-weight: 600;
  border-radius: 8px;
  margin: 10px 0px 10px 0px;
}

.select option{
  font-weight: 600;
  background: #23232d;
  border-radius: 8px;
  border: none;
}

#filter {
  position: sticky;
  top: 20px;
  width: 300px;
  height: 100%;
  margin: 10px;
  background-color: #23232d;
  padding: 10px;
  font-size: 15px;
  border-radius: 8px;
}

#filter b {
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}

.f-title {
  text-align: center;
  font-weight: 600;
  letter-spacing: 1px;
  text-transform: uppercase;
  margin-bottom: 20px;
}
.maker-count {
  color: #8c8c8c;
}

.makers,.condition {
  display: flex;
  flex-direction: column;
}

#filter .pretty {
  margin-bottom: 15px;
}

.category {
 color: #8c8c8c;
  letter-spacing: 1px;
}
#filter input {
  width: 50px;
  margin-bottom: 20px;
  background: transparent;
  border-top: none;
  border-left: none;
  border-right: none;
  border-bottom: 1px solid #7c7c7e;
  padding: 8px;
  margin-right: 20px;
  color: #cccccc;
  font-weight: 600;
  text-align: center;
  -webkit-appearance: none;
}
.price span {
  margin-right: 20px;
}

input[type='number'] {
  -moz-appearance:textfield;
}

input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
}
</style>