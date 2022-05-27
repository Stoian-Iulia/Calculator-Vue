<template>

    <div id="mainDiv">

        <div class="list">
            <ul>
                <li id="0" @click="showInfo">Stoian Iulia</li>
                <li id="1" @click="showInfo">Lidia Girleanu</li>
                <li id="2" @click="showInfo">Ion Neculesсu</li>
                <li id="3" @click="showInfo">Victor Nezdolii</li>
                <li id="4" @click="showInfo">Alina Cristian</li>
            </ul>
        </div>
        <div id="info">

        </div>
        
    </div>
    
</template>

<script>
export default ({
    data() {
      return {

        persons : [
            {
                name: "Stoian Iulia",
                age: 20,
                number: "+37368634824",
                adress: "Falesti",
            },
            {
                name: "Lidia Girleanu",
                age: 45,
                number: "+37344634824",
                adress: "Chisinau",
            },
            {
                name: "Ion Neculesсu",
                age: 54,
                number: "+37356518234",
                adress: "Balti",
            },
            {
                name: "Victor Nezdolii",
                age: 26,
                number: "+3736910387",
                adress: "Benderi",
            },
            {
                name: "Alina Cristian",
                age: 19,
                number: "+3734565875",
                adress: "Cahul",
            },
        ]
      }  
    },
    methods: {
        showInfo(event){
            let leftDiv = document.getElementById("info");
            leftDiv.innerHTML = "";
            for (const key in this.persons) {
                if (key == event.target.id) {
                    for (const par in this.persons[key]) {
                        console.log(par," : ",this.persons[key][par]);
                        let textInfo = document.createElement("p");
                        textInfo.textContent = `${par} : ${this.persons[key][par]}`;
                        leftDiv.appendChild(textInfo);
                    }                  
                }
            }
        
            console.log(event.target.id);
            
        }
  
    },
    computed: {
    
    }
})
</script>

<style scoped>
/* li{
    list-style: none;
} */
input{
    width: 120px;
}
#mainDiv{
    display: flex;
    width: 100%;
    justify-content:space-evenly;
    align-items:center;
}
</style>