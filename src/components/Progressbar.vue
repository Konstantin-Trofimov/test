<template>
    <div class="wrapper">
        <p class="title">Нагрузка преподавателей</p>
        <p class="subtitle">ПЛАНОВАЯ <span class="title">{{planLoad}} тыс. часов</span></p>

        <div class="progressbar">  
            <span 
                v-for="(i, index) in progressbar"
                :key=index
                :class="i.filled ? 'active' : 'b'"
                class="progressbar__item"
            ></span>
        </div>
        <div class="actualLoad">{{actualLoad}}%</div>
        <p class="subtitle">ФАКТИЧЕСКАЯ</p>
        <input 
            class="udateData"  
            type="text"
            v-model="factLoad"
            @input="inputChange()"
        >
    </div>
</template>

<script>
export default {
    name: 'progressbar',
    data() {
        return {
            planLoad: 9491,
            factLoad: 7400,
            progressbar: [
               {filled: false},
               {filled: false},
               {filled: false},
               {filled: false},
               {filled: false},
               {filled: false},
               {filled: false},
               {filled: false},
               {filled: false},
               {filled: false},
               {filled: false}
            ]
        }
       
    },
    methods: {
        inputChange() {
            let currentLoadView = Math.floor(this.actualLoad / 10);

            for (let i = 0; i < this.progressbar.length; i++) {
                if (i <= currentLoadView) {
                    this.progressbar[i].filled = true;
                }
                else {
                    this.progressbar[i].filled = false;
                }
            }
        }
    },
    computed: {
        actualLoad() { 
            return Math.floor((this.factLoad / this.planLoad) * 100 );
        }
    },
    mounted() {
        this.inputChange();
    }
}
</script>

<style>
    .wrapper {
        margin-top: 60px;
        width: 100vw;
        height: 300px;
        background: #0D1942;
        padding: 20px;
    }

    .title {
        font-size: 24px;
        font-weight: 700;
        color: #FFFF
    }

    .subtitle {
        margin-top: 5px;
        font-size: 18px;
        color: #485D83;
    }

    .progressbar {
        margin-top: 20px;
        height: 40px;
        display: flex;
    }

    

    .progressbar__item {
        width: 15px;
        height: 100%;
        margin-right: 5px;
        background: #1A5FC7;
        background: #0B2360;
       
    }

    .progressbar__item:first-child {
        width: 8px;
        background: #1A5FC7;
    }


    .actualLoad {
        margin-top: 10px;
        color: #1A5FC7;
        font-size: 36px;
        font-weight: 500px;
    }

    .udateData {
        display: block;
        margin-top: 50px;
        padding: 10px;
        border: none;
        color: #1A5FC7;
        font-size: 24px;
        font-weight: 600;
        background:  #0B2360;
    }

    .active {
         background: #1A5FC7;
    }

    .udateData:focus {
        outline: none;
    }
</style>