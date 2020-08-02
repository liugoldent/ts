<template>
  <div class="home">
    <input v-model="ParString.init">
    <!-- <button @click="fetchData(ParString)">toUpper</button> -->
    <h1>{{ParString.Upper}} </h1>
    <h2>Count is: {{ data.count }}, double is: {{ data.double }} </h2>
    <button @click="increment(data)">Click Me </button>
  </div>
</template>
<script lang="ts">
import { defineComponent, computed, reactive, ref } from '@vue/composition-api'

export default defineComponent({
  setup () {
      ///////////////////0717 Athena Question
      interface IParString {
        init:string,
        Upper:string
      }
      let ParString:IParString = reactive({
        init:'Hello World',
        Upper:computed(()=> ParString.init.toUpperCase())
      });

      ///////////////////0724 Athena Question
      // let a:number = 10
      // let b:string = '10'
      // let c:boolean = true
      // let d:undefined = undefined //null 為任何型別的子型別，故也可以設定為其他型別
      // let e:null = null //null 為任何型別的子型別，故也可以設定為其他型別
      // let f //我認為是any，因為如果是以型別推論來說，當賦值後才會決定型別。但以型別註記而言他是any
      // let g:number[] = [1, 2]
      // let h:(number | string)[] = [1, '2']

      // interface Iobject {
      //   x:number,
      //   y:string
      // }
      // let i:Iobject = { x: 5, y: '6'}


      ///////////////////0731 Interface
      interface A{
        x:number,
        y:string,
      }
      let a: A = {x:5, y:'6'}




      interface B{
        x:number,
        y:string,
        z?:boolean
      }
      let b:B = { x: 5, y: '6'}
      b.z = true




      interface C {
          [index: number]: number | string
          length: number
      }
      let c:C = [1, '2']




      interface D {
        (arg0:string):number
      }
      let d: D = function (arg0) {
          return Number(arg0)
      }
      let FuncResult = d('3')




      interface E {
        (arg0:string,arg1:string):string
      }
      let e: E = function (arg0, arg1): string {
          return arg0 + arg1
      }
      let FuncEResult = e('Hello', 'World')




      interface F {
          ():string
      }
      let f: F = () => 'Hello'
      console.log(f())




      interface G {
        (x:number,y:number): number
      }
      let g: G = (x: number, y: number) => x + y




      interface H {
          (x:number) : void
      }
      let cb = function (x: number) {
          cb(x + 1)
      }
      let h: H = (cb) => { }
      let testResult = h(3)
      console.log(testResult)




      interface I {
          [key:number]: string
      }
      let i: I = {}
      i = { 1: 'a' }
      console.log(i)

      /////////////////// Vue3 Used
      let state: number = 0

      let PlusOne : object= computed({
        get: () => {console.log(state)},
        set: val => { state = state - 1 }
      })

      const increment = function(data:IdataInter): void{
        data.count++
        console.log(data)
      }
      interface IdataInter {
        count : number;
        double: number
      }

      let data:IdataInter = reactive({
        count : 2,
        double:computed(()=>{
          return data.count*2
        }),
        triple:computed(()=>{
          return data.count^3
        })
      })

      return {
          //0717
          ParString,

          //0724
          state,
          PlusOne,
          increment,
          data
      }
  }
});
</script>
