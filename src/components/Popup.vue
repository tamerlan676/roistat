<template>
    <div class="popup">
        <header>
            <h3>Добавить пользователя</h3>
        </header>
        <label for="">Введите имя</label>
        <input type="text" v-model="name">
        <label for="">Введите номер телефона</label>
        <input type="text" v-model="phone">
        <label for="">Укажите начальника</label>
        <select v-model="selected" name="" id="">
            <option></option>
            <option  v-for="(item, key) in table" :key="key" >{{ item.name }}</option>
        </select>
        <button @click="addPerson">Добавить</button>
    </div>
</template>

<script>

export default ({
        data(){
        return{
                name: '',
                phone: '',
        }
    },
    props: ['table'],
    methods: {
        addPerson(){
            if(this.name !== '' && this.phone !== ''){
            this.table.push({
                name: this.name,
                phone: this.phone,
            });
            this.name = '';
            this.phone = '';
            localStorage.setItem("table", JSON.stringify(this.table));
            }
        }
    }
})
</script>


<style>
.popup{
    position: absolute;
    width: 300px;
    height: 400px;
    right: -100%;
    top: 40px;
    background: rgb(226, 226, 226);
    padding: 20px;
    display: flex;
    flex-direction: column;
    transition: all .5s ease;
    border-radius: 10px;
}

header{
    display: flex;
    justify-content: space-between;
    margin-bottom: 20px;
}
img{
    width: 30px;
    cursor: pointer
}

label{
    margin-bottom: 4px;
    font-weight: 500;
}

input{
    height: 30px;
    margin-bottom: 16px;
    border: none;
}

select{
    height: 30px;
    margin-bottom: 16px;
    border: none;
}

button{
  padding: 10px;
  border: none;
  background: orange;
  border-radius: 5px;
  color: #fff;
  cursor: pointer
}
</style>