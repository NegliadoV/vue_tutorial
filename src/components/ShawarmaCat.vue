<template>
    <div class="cat">

        <div> <img :style="imageFilters" :class="imageSizes" v-show="isCatVisible" class="img"
                src="../assets/image/cat.jpg" alt="#">
        </div>
        <div>
            <h2>Пица кот</h2>
            <button @click="imageSizes.sepia = !imageSizes.sepia" class="btn" type="button">Сепия</button>
            <button @click="imageSizes.border = !imageSizes.border" class="btn" type="button">Рамка</button>
            <button @click="imageSizes.reduce = !imageSizes.reduce" class="btn" type="button">Уменьшить</button>
            <button class="btn" @click="isCatVisible = !isCatVisible">
                {{ textButton }}</button>


            <div style="display:flex"><label>Ширина: {{ imageFilter.currentWidth }}
                    <input @input="imageFilter.currentWidth = $event.target.value" :value="imageFilter.currentWidth"
                        type="range" :min="imageFilter.minWidth" :max="imageFilter.maxWidth">
                </label>
                <label>Высота: {{ imageFilter.currentHeight }}
                    <input @input="imageFilter.currentHeight = $event.target.value" :value="imageFilter.currentHeight"
                        type="range" :min="imageFilter.minHeight" :max="imageFilter.maxHeight">
                </label>
                <label>Поворот: {{ imageFilter.currentRotate }}
                    <input @input="imageFilter.currentRotate = $event.target.value" :value="imageFilter.currentRotate"
                        type="range" :min="imageFilter.minRotate" :max="imageFilter.maxRotate">
                </label>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ShawarmaCat',
    data() {
        return {
            isCatVisible: true,
            visibleText: 'Скрыть кота',
            noVisibleText: 'Вернуть котана',
            imageSizes: {
                sepia: false,
                border: false,
                reduce: false,
            },
            imageFilter: {
                maxWidth: 680,
                minWidth: 0,
                maxHeight: 480,
                minHeight: 0,
                currentWidth: 680,
                currentHeight: 480,
                maxRotate: 360,
                minRotate: 0,
                currentRotate: 360,
            }
        }
    },


    computed: {
        textButton() {
            if (this.isCatVisible === true) {
                return this.visibleText
            }

            if (this.isCatVisible === false) {
                return this.noVisibleText
            }
        },
        imageFilters() {
            return {
                width: `${this.imageFilter.currentWidth}px`,
                height: `${this.imageFilter.currentHeight}px`,
                transform: `rotate(${this.imageFilter.currentRotate}deg)`,
            }
        }
    },
    methods: {

    }
}
</script>

<style>
.cat {

    margin: 0 auto;
    padding: 0 5vh;
    display: flex;
    justify-content: center;
    align-items: center;

}

.img {
    max-width: 100%;
    max-height: 100%;
}



.btn {
    font-size: 16px;
    margin: 5px;
    border-radius: 3px;
    border: 1px #ccc solid;
    background-color: #fff;
}

.btn:hover {
    background-color: #369999;
}

.img.sepia {
    filter: sepia(1);
}

.img.border {
    border: 5px dashed #369999;
}

.img.reduce {
    max-width: 10%;
    max-height: 10%;

}
</style>