<template>
  <div class="user_cad">
    <h1>Научу зарабатывать от 500 000р. в час </h1>
    <div class="miain_information">
      <img class="img_brutal" src="../assets/image/brutal.jpg" alt="#">
      <div class="info">
        <h2>
          {{ getAuthorFullName }}
        </h2>
        <strong>Бизнес-коуч</strong>
        <ul>
          <li>Учу людей делать реальные БАБКИ, на себя просто не хватило времени</li>
          <li>Не знаю, что такое "Успешный успех"б но знаю что нужно ТЕБЕ!</li>
          <li>Пообещал что по бреюсь когда кого нибудь ОБМАНУ!</li>
        </ul>
      </div>
    </div>
    <p>Учасников: : {{ users.length }}</p>
    <ul>
      <li v-for="(user, id) in users" :key="id">
        {{ `${id + 1} ${getFullName(user)} ` }}</li>
    </ul>
    <button type="button" @click="currentPages--">Пред</button>
    <button type="button" v-for="page in pages" :key="page" @click="currentPages = page">{{ page }}</button>
    <button type="button" @click="currentPages++">След</button>

  </div>
</template>

<script>

export default {
  name: "MyComponent",

  data() {
    return {

      min: 1,

      firstName: 'Иван',
      secondName: 'Витальевич',
      lastName: 'Богатов',
      users: [
        {
          firstName: 'Сергей',
          secondName: 'Сергеевич',
          lastName: 'Сергеев',
        },
        {
          firstName: 'Виталий',
          secondName: 'Витальевич',
          lastName: 'Виталов',
        },
        {
          firstName: 'Игнатий',
          secondName: 'Илларионович',
          lastName: 'Романов',
        },
      ],
      pages: 3,
      currentPages: 1,

    };
  },

  computed: {
    getAuthorFullName() {
      return `${this.firstName} ${this.secondName} ${this.lastName}`.toUpperCase()
    }
  },

  methods: {
    getFullName(user) {
      return `${user.firstName} ${user.secondName} ${user.lastName}`
    },
    loadUsers(page) {
      console.log(`Загрузка пользователей: Страница ${page}`)
    }
  },

  watch: {
    currentPages(newValue) {
      this.loadUsers(newValue)
      if (this.currentPages < this.min) {
        this.currentPages++
      }
      if (this.currentPages > this.pages) {
        this.currentPages--
      }

    }
  }
};
</script>

<style>
.img_brutal {
  width: 250px;
  height: 350px;
  margin-right: 10px;
}

.miain_information {
  display: flex;
}
</style>
