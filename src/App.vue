<template>
<div>{{greet}} {{name}}</div>
<button :disabled="isDisabled">Bind</button>
<h2 :class="status">underlined Text</h2>
<h2 :class="isPromoted ? 'promoted' : ''">Promoted Movie</h2> 
<h2 :class="isSoldout ? 'sold-out' : 'new'">Movie </h2> 
<h2 :class="['new' , 'promoted']">Newly Promoted Movie</h2>
<h2 :class="[isPromoted && 'promoted' , isSoldout ? 'sold-out' : 'new']">Array Condational movie</h2>
<h2 :class="{
  promoted: isPromoted , 
  'new': !isSoldout , 
  'sold-out': isSoldout
}">object condational Movie
</h2>
<h2 :style="{
  color: color , 
  'font-size' : fontSize + 'px' , 
  margin: 0  
}">Highlited Text</h2>
<!-- Apply Number of styling --> 
 
<h2 :style="cssStyling">Style Object </h2> 
<h2 v-if="num === 0">the number is zero</h2>
<h2 v-else-if="num < 0">the number is negative</h2>
<h2 v-else-if="num > 0">the number is positive</h2>
<h2 v-else>this isn't a number</h2>

<template v-if="display"><h1>hello world</h1> </template> 
<!-- template in this case act as a wrapper like div , but without applying stylying to it  -->
<h2 v-for="(name , index) in names" :key="name"> {{ index + 1 }} {{ name }}</h2>
<h2 v-for="name in fullnames" :key="name.first">{{name.first}} {{name.last}}</h2>
<div v-for="actor in actors" :key="actor">
{{ actor.name }}
<h3 v-for="movie in actor.movies" :key="movie">{{ movie }}</h3>
</div>
<h3 v-for="(value , key , index) in myinfo" :key="value">  {{index+1}} {{ key }} :{{ value }}</h3>
<hr />

<!-- <template v-for="name in names" :key="name">
<h2>{{name}}</h2> 
<input placeholder="Last Name">
<hr />
</template>

<template v-for="name in names" :key="name">
 <h2 v-if="name === 'osama'">{{ name }}</h2>
</template> -->

<!-- if we want to use v-if and v-for together we must use template -->
<h2>{{overalltax(1000)}}</h2>
<h2>{{newname}}</h2>
<div>
  <button v-on:click="changename">change name</button>
</div>
<h1>{{count}}</h1>
<h1>{{count2}}</h1>



<div>
  <button @click="count +=1">استغفرالله</button>
  <button v-on:click="count2 +=1">سبحان الله</button>

</div>
<form @submit.prevent="submitForm">

<div style="margin-top:20px">
  <label for="name">Name</label>
  <input type="text" name="" id="" v-model.trim="formvalues.name">
</div>
{{formvalues.name}}
<div>
  <label for="profile">Profile Summary</label>
  <textarea id="profile" v-model="formvalues.profileSummary"></textarea>
</div>
{{formvalues.profileSummary}}
<div>
  <label for="country">Country</label>
  <select id="country" v-model="formvalues.country">
  <option value="">select a country</option>
  <option value="india">India</option>
  <option value="Vietnam">Vietnam</option>
  <option value="Singaphore">Singaphore</option>
</select>
{{formvalues.country}}

</div> 

<div>
  <label for="job-location">job Location</label>
  <select id="job-location" multiple v-model="formvalues.jobLocation">
  <option value="india">india</option>
  <option value="vietnam">Vietnam</option>
  <option value="singaphore">Singaphore</option>
</select>

</div>
<div>
  <input type="checkbox" id="remote" v-model="formvalues.remoteWork" true-value="yes" false-value="no"> 
  <label for="remote">Open to remote Work ?</label>
</div> 
  {{formvalues.remoteWork}}
  <div>
    <label>Skills Set</label>
    <input type="checkbox" id="html" value="html" v-model="formvalues.skills">
    <label for="html">  HTML</label>
    <input type="checkbox"  id="css" value="css" v-model="formvalues.skills">
    <label for="css">CSS</label>
    <input type="checkbox" id="javascript" value="javascript" v-model="formvalues.skills">
    <label for="javascript">JS</label>
  </div>
  <div>
    <label>Years Of Experience</label>
    <input type="radio" id="0-2" value="0-2" v-model="formvalues.yearsofexperience">
    <label for="0-2">0-2</label>
    <input type="radio" id="3-5" value="3-5" v-model="formvalues.yearsofexperience">
    <label for="3-5">3-5</label>
    <input type="radio" id="6-10" value="6-10" v-model="formvalues.yearsofexperience">
    <label for="6-10">6-10</label>
    <input type="radio" id="+10" value="+10" v-model="formvalues.yearsofexperience">
    <label for="+10">+10</label>
  </div>
  {{formvalues.yearsofexperience}}
  <div style="margin-bottom:10px">
    <label for="age">Age</label>
    <input @keyup.enter="submitForm" type="number" id="age" v-model.number="formvalues.age">
  </div>
  <div>
    <button>Submit</button>
  </div>
  
</form>
<h2>{{firstName}} {{lastName}}</h2>
<h2>{{displayFullname}}</h2>
<h2>{{fullnameDisplay()}}</h2>
<h2> Computed - {{totalPrice}}</h2> 
<h2> Function - {{priceTotal()}}</h2>
<button @click="items.push({id:4 , title: 'keyBoard' , price: 600})">Add Item</button>
<!-- <template v-for="item in items" :key="item.id">
<h2 v-if="item.price > 100">{{item.title}} {{item.price}}</h2>
the old way to compine v-for and v-if
</template> -->

<h2 v-for="item in filterItems" :key="item.id">{{item.title}} - {{item.price}}</h2>
<!-- the new item depends on filtering the item [condation] in a computed proprty  -->
<h2>Volume Tracker (0-20)</h2>
<h3>current volume => {{volume}}</h3>
<div>
  <button @click="volume +=2">increase volume</button>
  <button @click="volume -= 2">decrese volume</button>

</div>
<input type="text" v-model="movie">
<input type="text" v-model="movieInfo.title">
<input type="text" v-model="movieInfo.actor">
<button @click="movieList.push('WonderWoman')">Add movie</button>
<greetPrint name="Abdullah" heroName="mohammed"></greetPrint>
<greetPrint name="Osama" heroName="Ali"></greetPrint>
<greetPrint :name="Fname" :heroName="Aka">Hello world</greetPrint>
<!-- You can use props to identify properties of the component, and for the aactual data you use data()  -->
<ArticleComponent :title="title" :likes="500000"  :isPublished="false"  style="color: green;"  />
<!-- Always use bind when you input value integer or boolean in props like the case in likes -->

<componentC></componentC>
<h3>AppComponent Username -  {{injectname}}</h3>
  <button @click="showPopup = true">Show Pop Up</button>
  <PopUpComponent name="Closing Now" v-show="showPopup" @close="popupFunction" />
  <InputComponent v-model="componentName"/> 
  <CardComponent content="This is My Card Number 1" />
  <card-component>Hello World</card-component>
  <card-component><h2>Hello WORLD</h2></card-component>
  <card-component><img src="https://picsum.photos/200" /></card-component>
<card-component>
  <template v-slot:header >
    <h1>HEADER</h1>
  </template>
  <template v-slot:default>
    <img src="https://picsum.photos/200">
  </template> 
  <template v-slot:footer> 
    <button>View Details</button>
  </template>
</card-component>
<NameList>
  <template v-slot:default="slotProps">
    {{slotProps.firstName}} {{slotProps.lastName}} 
  </template>
</NameList>
<NameList>
  <template v-slot:default="slotProps">
    {{slotProps.lastName}} 
  </template>
</NameList>

<salesComponent>
  <template v-slot:default="slotProps"> 
    {{slotProps.ProductName}} - {{slotProps.price}}
  </template>
</salesComponent>

<StudentsComponent>
  <template v-slot:default="slotProps">
  ID => {{slotProps.id}} Name => {{slotProps.firstName}} City =>{{slotProps.city}}
  </template>
</StudentsComponent>
<div style="display: flex; gap: 4.2px;">
  <button style="padding: 4px 10px;" @click="activeTab ='tabA' ">Semester 1</button>
  <button style="padding: 4px 10px;"  @click="activeTab ='tabB' ">Semester 2</button>
  <button @click="activeTab ='tabC' ">Semester 3</button>
</div>
<keep-alive>
<component :is="activeTab" /> 
</keep-alive>

<!-- this to replace the v-if 
<tabA v-if="activeTab === "tabA"" />
<tabA v-if="activeTab === "tabB"" />
<tabA v-if="activeTab === "tabC"" />


-->

</template>   
<script> 
import greetPrint from './assets/components/greet.vue' 
import ArticleComponent from './assets/components/Article.vue' 
import componentC from './assets/components/componentC.vue' 
import PopUpComponent from './assets/components/Popup.vue'
import InputComponent from './assets/components/input.vue'
import CardComponent from './assets/components/card.vue' 
import NameList from './assets/components/NameList.vue'
import SalesComponent from './assets/components/SalesComponent.vue'
import StudentsComponent from './assets/components/students.vue'
import tabA from './assets/components/tabA.vue' 
import tabB from './assets/components/tabB.vue' 
import tabC from './assets/components/tabC.vue' 

export default{
  name: 'App' , 
  components: {
    PopUpComponent,
    greetPrint,
    ArticleComponent , 
    componentC,
    InputComponent ,
    CardComponent , 
    NameList , 
    SalesComponent , 
    StudentsComponent ,
    tabA , 
    tabB , 
    tabC
  },
  data() {
    return {
      activeTab: '' , 
      componentName: '' , 
      showPopup:false , 
      injectname : 'Abdullah' , 
      title : 'Blood and Fire' , 
      Fname: 'Abdullah' , 
      Aka : 'Aljehani' , 
      movie: 'Batman' ,
      movieInfo: {
        title: 'Based on true story' ,
        actor: 'Bruce Wayne'
      }  ,
      movieList: [
        'Batman' , 'SuperMan'
      ],
      volume: 0 , 
      namechange: ['osama' , 'Ahmed' , 'omar'] , 
      yourname: 'sufyan' , 
      firstName: 'Abdullah' , 
      lastName: 'Aljehani' , 
      items: [

        {
          id:1 , 
          title: 'TV' , 
          price: 100
        
        },

        {
          id:2 , 
          title: 'Phone' , 
          price: 300

        },

        {
          id: 3 , 
          title: 'laptop' , 
          price: 400

        }
      ] , 
      formvalues: {
        name: '' , 
        profileSummary: '' , 
        country: '' , 
        jobLocation: [] , 
        remoteWork: 'no' , 
        skills: [] , 
        yearsofexperience: '' , 
        age: null
      } , 
      count: 0 , 
      count2: 0 , 
      newname: 'Abdullah' , 
      AddedTax : 20 , 
      myinfo: {
        name: 'Abdullah' , 
        channel: 'Abdullah.channel' , 
        subscribers: 12000000
      } , 
      actors: [
        {
          name: 'chris bale' , 
          movies: ['batman' , 'the prestige'] , 
        } , 
        {
          name: 'di caprio' , 
          movies: ['titanic' , 'inception']
        }
      ] , 
      names: [
        'mohammed' , 
        'Ali'  ,
        'osama'
      ] , 
      fullnames: [
        {first: 'Abdullah' , last: 'Aljehani'} , 
        {first: 'osama' , last: 'Ahmed'} , 
        {first: 'osama' , last: 'Ali'}
      
    ],
      display: true,
      num : 3 ,       
      name: 'osama' ,
      greet : 'hello' ,
      isDisabled: true , 
      status: 'Success' , 
      isPromoted: true , 
      isSoldout: false ,
      color: 'gray' , 
      fontSize: 50 , 
      cssStyling: {
        color: 'yellow' , 
        fontSize: '30px' ,

      }
    } ;
  },
  methods: {
    popupFunction(name) {
      this.showPopup = false
      console.log('name' , name)
    } , 
  overalltax(tax) {
    return tax + this.AddedTax
// when reciving from data property , always use this
  } , 
  changename() {
    this.newname = this.names[this.count] 
    this.count ++ 
  } , 
  submitForm() {
console.log('Form values' , this.formvalues)
  } , 
  fullnameDisplay() {
    return `${this.firstName} ${this.lastName}`
  } , 
  priceTotal() {
    return this.items.reduce((total, curr) => (total = total + curr.price) , 0 )

  } , 
  incresevolume() {
       this.value = this.value + 2
    }
  
  } , 
  computed: {
    displayFullname() {
      return `${this.firstName} ${this.lastName}`
    } , 
    totalPrice() {
      return this.items.reduce((total, curr) => (total = total + curr.price) , 0 )
    } ,
    filterItems() {
      return this.items.filter(item=> item.price > 100)
    },
   
    
  } ,
  // used to watch the data properties and computed properties when some event occur 
  watch: {
    volume(newvalue, oldvalue) {
      if(newvalue > oldvalue && newvalue === 16) {
        // to ensure that we increasing not decresing 
        alert('Listening to a high volume for a long time may damage your hearing')
      }
    } , 
    movie: {
      handler(newvalue) {
        console.log(`Calling an API with movie name = ${newvalue}`)
      } , 
      immediate: true , 
      // this structure helps when there no update on value , but still want to scearch 
      // immediate run = true
    } , 
    movieInfo: {
      handler(newvalue) {
        console.log(`Calling an API with movie title = ${newvalue.title} and actor = ${newvalue.actor}` )
      } , 
      deep: true ,
            // Deep = allow us to watch object data properties

      immediate: true
    } , 
    movieList: {
      handler(newvalue) {
        console.log(`Current value = ${newvalue}`)
      } , 
      deep: true ,
      immediate: true 
    }
   

  } , 
  provide() {
    return {
      username: this.injectname
    }
  }
  }
 

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
  display: grid; 
  place-items: center;
}
.underlined {
  text-decoration: underline;
}
.Success {
  color: red;
} 
.promoted {
  font-style: italic;
  color: orange; 
  
}
.sold-out {
  color: red;
} 
.new {
  color: green;
}
label {
  font-weight: bold; 
  display: flex; 
  margin-bottom: 5px;
} 
input + label {
  font-weight: bold; 
  display: inline-flex; 
  margin-right: 20px;
}
input[type='text'],
textarea, 
select {
  display: block; 
  width: 400px; 
  padding: 6px 12px; 
  font-size: 14px; 
  line-height: 1.4285371; 
  color: #555; 
  background-color: #fff; 
  background-image: none;
  border: 1px solid #ccc; 
  border-radius: 4px;

}

</style>
