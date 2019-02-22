<template>
    <div class="add-dvd">
        <div class="add">
            <div class="plus-minus-toggle collapsed" 
                @click="toggleAdd"></div>
        </div>

        <form @submit="addDVD" ref="slidingForm" class="hidden" autocomplete="off">
            <input type="text" v-model="title" name="title" required
                placeholder="New Title"><br/>
            <input type="text" v-model="category" name="category" required
                placeholder="Category"><br/>
            <input type="number" v-model="runtime" name="runtime" required
                placeholder="Runtime (minutes)"><br/>
            <input type="number" min="1880" v-model="year" name="year" required
                placeholder="Year"><br/>
            <input type="number" step="0.01" v-model="price" name="price" required
                placeholder="Price (USD)"><br/>

            <input type="submit" value="ADD" class="btn">    
        </form>
    </div>

</template>

<script>
export default {
    name: "AddDVD",
    data() {
        return {
            title: '',
            category: '',
            runtime: '',
            year: '',
            price: ''
        }
    },
    methods: {
        addDVD(e) {
            // prevent reload on submit
            e.preventDefault();

            const newDVD = {
                title: this.title,
                category: this.category,
                runtime: this.runtime,
                year: this.year,
                price: this.price
            }

            // Send up to parent
            this.$emit('add-DVD', newDVD);

            // Clear form
            this.title = '';
            this.category = '';
            this.runtime = '';
            this.year = '';
            this.price = '';
        },
        toggleAdd() {
            event.target.classList.toggle('collapsed');
            this.$refs.slidingForm.classList.toggle('hidden');
        }

    }
}
</script>

<style scoped>
.add {
    display: flex;
    align-items: center;
    justify-content: center;

    width: 100%;
    height: 50px;

    margin: 1em 0 0;
    padding-top: .6em;

    background-color: #666;
    color: white;
}

.add-dvd form {
    padding: 1em 0 ;
    background-color: #aaa;
    max-width: 95%;
    margin: 0 2.5%;
}

.add-dvd form input {
    width: calc(100% - 2em);
    margin: 0 1em;

    box-sizing: border-box;
	-webkit-box-sizing: border-box;
	-moz-box-sizing: border-box;
	outline: none;
	display: block;
	padding: 2px;
	border: none;
	border-bottom: 1px solid #ddd;
	background: transparent;
	margin-bottom: 10px;
	font-size: 14px;
	height: 25px;
}

.add-dvd form input::placeholder {
    color: #ddd;
}

.add-dvd form input[type="submit"],
.add-dvd form input[type="button"]
{
	position: relative;
	display: block;
	padding: 10px 39px 28px 39px;
	color: #FFF;
	margin: 0 auto;
	background: #bbb;
	font-size: 16px;
	text-align: center;
	font-style: normal;
	width: 50%;
	border: 1px solid #999;
	border-width: 1px 1px 3px;
	margin-bottom: 0px;
}
.add-dvd form input[type="submit"]:hover,
.add-dvd form input[type="button"]:hover
{
	background: #999;
}


.plus-minus-toggle {
  cursor: pointer;
  height: 21px;
  position: relative;
  width: 21px;
}
.plus-minus-toggle:before,
.plus-minus-toggle:after {
  background: white;
  content: '';
  height: 5px;
  left: 0;
  position: absolute;
  top: 0;
  width: 21px;
  transition: transform 500ms ease;
}
.plus-minus-toggle:after {
  transform-origin: center;
}
.plus-minus-toggle.collapsed:after {
  transform: rotate(90deg);
}
.plus-minus-toggle.collapsed:before {
  transform: rotate(180deg);
}

.hidden {
    display: none;
   
}


</style>

