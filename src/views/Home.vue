<template>
    <div>
        <h1>Welcome to {{title}},{{title2}}</h1>
        <input type="text" v-model="input1" />
        <button type="button" @click="getDate">get</button>
        <button type="button" @click="setDate">set</button>

        <select class="form-control" v-model="region" @change="changeRegion">
             <option :key="index" :value="data.v" v-for="(data,index) in options">{{data.t}}</option>
            
        </select>

        <!-- <table class="table table-bordered" v-if="tableShow"> -->
        <table class="table table-bordered" v-show="tableShow">
            <tr :key="index" v-for="(data,index) in options">
                <td>{{data.v}}</td>
                <td>{{data.t}}</td>
            </tr>

        </table>

    </div>
</template>
<script>
export default {
    data() {
        return{
            title : "개발자의 품격",
            title2: "Seoul",
            input1: "abc",
            options: [
                { v:"S",t:"Seoul"},
                { v:"J",t:"Jeju"},
                { v:"B",t:"Busan"},
            ],
            region: "J",
            tableShow:false,
        };
    },
    
    watch:{
        input1(){
            console.log(this.input1);
        }
        
    },

    methods: {
        getDate(){
            alert(this.input1)
        },
        setDate(){
            this.input1 = "12345";
        },
        changeRegion(){
            alert(this.region);
        },
    },
        beforeCreate(){ console.log("beforeCreate");},
        created(){console.log("created");},
        beforeMount(){console.log("beforeMount");},
        mounted(){console.log("mounted");},
        beforeUpdate(){console.log("beforeUpdate");},
        updated(){console.log("updated");},
        beforeDestroy(){console.log("beforeDestroy");},
        destroyed(){console.log("destroyed");}
    

};
</script>