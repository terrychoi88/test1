<template>
   <div>
       <h1>Welcome to {{title}}!</h1>
       <input type="text" v-model="input1" />
       <button type="button" @click="getData">Get</button>
       <button type="button" @click="setData">Set</button>
       <select class="form-control" v-model="region" @change="changeRegion">
           <option :key="i" :value="d.v" v-for="(d,i) in options">{{d.t}}</option>
       </select>

       <button type="button" @click="tableButton">tableButton</button>

       <table class="table table-bordered" v-show="tableShow">
           <tr :key="i" v-for="(d,i) in options">
               <td>{{d.v}}</td>
               <td>{{d.t}}</td>
           </tr>
       </table>
   </div> 
</template>
<script>
export default {
    data() {
        return {
            title: "Terry's World",
            input1: "abcd",
            options: [
                {v:"S", t:"Seoul"},
                {v:"J", t:"Jeju"},
                {v:"B", t:"Busan"}
            ],
            region: "J",
            tableShow: false,
        };
    },
    watch: {
        input1() {
            console.log(this.input1);
        }
    },
    methods: {
        tableButton() {
            if(this.tableShow==true){
                this.tableShow = false;
            } else {
                this.tableShow = true;
            }
        },
        changeRegion() {
            alert(this.region);
        },
        getData() {
            alert(this.input1);
        },
        setData() {
            this.input1 = "12345";
        },
        beforeCreate() {
            console.log("beforeCreate");
        },
        created() {
            console.log("created");
        },
        beforeMount() {
           console.log("beforeMount");
        },
        mounted() {
           console.log("mounted");
        },
        beforeUpdate() {
           console.log("beforeUpdate");
        },
        updated() {
           console.log("updated");
        },
        beforeDestroy() {
           console.log("beforeDestroy");
        },
        destroyed() {
           console.log("destroyed");
        }
    }
};
</script>