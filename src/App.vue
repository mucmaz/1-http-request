<template>
  <div class="container">
    <h3>Alışveriş Listesi</h3>
    <hr/>
    <div class="my-2">
        <input type="text" placeholder="ne alacaksın" @keydown.enter="onSave" />
    </div>
    <ul class="list-group">
      <li class="d-flex justify-content-between align-items-center list-group-item list-group-item-action">
        <span>Eleman 1</span>
        <button class="btn btn-danger">Sil</button>
      </li>
            <li class="d-flex justify-content-between align-items-center list-group-item list-group-item-action">
        <span>Eleman 1</span>
        <button class="btn btn-danger">Sil</button>
      </li>
            <li class="d-flex justify-content-between align-items-center list-group-item list-group-item-action">
        <span>Eleman 1</span>
        <button class="btn btn-danger">Sil</button>
      </li>
            <li class="d-flex justify-content-between align-items-center list-group-item list-group-item-action">
        <span>Eleman 1</span>
        <button class="btn btn-danger">Sil</button>
      </li>
            <li class="d-flex justify-content-between align-items-center list-group-item list-group-item-action">
        <span>Eleman 1</span>
        <button class="btn btn-danger">Sil</button>
      </li>
    </ul>
    <small class="badge badge-primary text-danger">5 Adet alınacak ürün vardır</small>
    </div>
</template>


<script>

import axios from "axios";

export default {
  data (){
    return {

    }
  },
  methods: {
    onSave(e){
      const saveObject = {title:e.target.value, createdDate: new Date(), complated: false };
      axios.post("http://localhost:3000/items", saveObject)
      .then(response => {
        console.log(response);
      }).catch(err => {
        console.log(err);
      })
    }
  }
}
</script>