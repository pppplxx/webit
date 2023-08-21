<template>
    <div>
      <br><br><br>
      <div class="d-flex justify-content-center">
        <div class="card mb-3" style="max-width: 600px;">
            <div class="row g-0">
              <div class="col-md-4">
                <img :src="picture" class="img-fluid" alt="...">
                
              </div>
              <div class="col-md-8">
                <div class="card-body">
                  <h5 class="card-title">Name : {{ getfullname() }}</h5>
                  <div class="d-flex justify-content-start rounded-3 p-2 mb-2"
                  style="background-color: #efefef;">
                  <div>
                    <p class="small text-muted mb-1">Student Id.</p>
                    <p class="mb-1">66309010017</p>
                    <form @submit="submitForm">
                    <div class="input-group mb-1">
                    <input type="text" class="form-control" placeholder="" aria-label="Example text with button addon" aria-describedby="button-addon1" @input="setNickName">
                    <button class="btn btn-outline-secondary" type="submit" id="button-addon1">Submit</button>
                    </div>
                    </form>
                    <p class="mb-1">Nickname : {{ nickname }}</p>
                    <p class="mb-1">Age : {{ age }}</p>
                    <p class="mb-1">Address : <span v-html="address"></span></p>
                  <p v-if="hobby.length === 0 ">ไม่มีงานอดิเรก</p>
                  <div v-else>
                    <p class="mb-1">Hobbies :</p>
                    <ul>
                      <li>{{ hobby[0] }}</li>
                      <li>{{ hobby[1] }}</li>
                    </ul>
                  </div>    
                    <div class="butt" style="margin-left: 43px;">
                    <button @click="showdata" style="background-color: green; border: none; color: white; border-radius: 3px; margin-right: 15px; padding: 5px;">Click me!</button>
                    <button @click="increment(10)" style="background-color: blue; border: none; color: white; border-radius: 3px; margin-right: 15px; padding: 5px;">increase!</button>
                    <button @click="decrement(3)" style="background-color: red; border: none; color: white; border-radius: 3px; margin-right: 15px; padding: 5px;">decrease!</button>
                  </div>
                  </div>
                  </div>
                </div>
                </div>
              </div>
            </div>
          </div>
    </div>
    <br><br>
  </template>
  <script>
  export default{
    data(){
        return{
            firstName : 'Suphawit',
            lastName : 'Lakmek',
            age : 18,
            address : '<i>Chonburi</i>',
            picture : 'https://i.pinimg.com/564x/73/89/26/738926d439337f8a6df535dc02b37a5e.jpg',
            size : 300,
            hobby:[ 'Listening music','Play games' ],
            general: {gender:'Male',weight:120,height: 178,status : false},
            nickname: ''
            }
        },
        methods: {
            getfullname(){
                return `${this.firstName} ${this.lastName}` 
            },
            showdata(){
                alert(this.getfullname())
            },
            increment(value){
              this.age += value
            },
            decrement(value){
              this.age -= value
            },
            setNickName(event){
              this.nickname=event.target.value
            },
            submitForm(e){
              e.preventDefault();
              alert('บันทึกข้อมูลเรียบร้อย')
            }
    }
  } 
  </script>
  <style>
  *{
    margin: 0;
  }
  </style>
  