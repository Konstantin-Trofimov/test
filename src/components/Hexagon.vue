<template>
    <div class="wrapper wrapper_hexagon">
        <div class="hexagon">
            <div class="hexagon__left-corner"></div>
            <p> ПРИОРИТЕТ 2030</p>
            <div class="hexagon__right-corner"></div>
        </div>
    </div>
</template>


<style scoped>

    .wrapper_hexagon {
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;
    }

    .hexagon {
        border: 2px solid #F1952B;
        width: 300px;
        height: 100px;
        position: relative;
        z-index: 1;
        flex-direction: column;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .hexagon p {
        font-size: 28px;
        font-weight: 700;
        color: #F1952B;
    } 

    .hexagon__left-corner {
        content: '';
        position: absolute;
        border-bottom: 2px solid #F1952B;
        width: 70px;
        height: 30px;
        top: -15px;
        left: -12px;
        transform: rotate(333deg);
        z-index: 2;
        background: #0D1942;
    }

    .hexagon__right-corner {
        content: '';
        position: absolute;
        border-top: 2px solid #F1952B;
        width: 70px;
        height: 30px;
        top: 82.5px;
        left: 242px;
        transform: rotate(333deg);
        z-index: 2;
        background: #0D1942;
    }


</style>