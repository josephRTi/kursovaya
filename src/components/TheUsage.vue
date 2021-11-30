<template>
  <div class="container with-nav">
    <div class="card-flex">
      <div class="item2">
        <h3>Использование NoSQL</h3>
        <hr>
        <p>NoSQL хранилища данных отвечают за те ключевые требования хранения данных, которые не могут быть удовлетворены
          реляционными БД.</p>
      </div>
      <div class="item2-img">
        <img class="responsive usage-img" src="https://www.cloudsavvyit.com/p/uploads/2021/07/f5932bc2.jpg?width=1198&trim=1,1&bg-color=000&pad=1,1" width="400" height="225" alt="mongo">
      </div>
    </div>
    <div class="card-flex">
      <div class="item2">
        <h3>Кеширование</h3>
        <hr>
        <p>
          Кеширование результатов является общей задачей повышения отзывчивости приложения. К примеру, web-сайт отдает одни
          и те же ответы сотням и тысячам пользователей. Вместо того, чтобы утомительно пересчитывать в реляционной БД одно
          и то же, стоит вручную настроить кеширование. Некоторые NoSQL хранилища предоставляют похожие решения, но
          разработчику не нужно поддерживать пользовательский кеш.
        </p>
      </div>

      <div class="item2-img">

        <br>
        <img class="responsive usage-img" src="https://marvel-b1-cdn.bc0a.com/f00000000173332/www.openlogic.com/sites/openlogic/files/image/2021-06/image-blog-openlogic-what-is-mongodb.png" alt="" width="450">
      </div>

    </div>

    <div class="card">
      <h3>Хранилища ключ-значение</h3>
      <hr>
      <p>
        Некоторые NoSQL БД сохраняют пары ключ-значение для быстрого поиска, к примеру, в случае доступа вопрос/ответ.
        Реляционные БД более ориентированы на сохранение сложных структур данных и различных взаимосвязей между типами
        данных. Эта технология излишне усложняет, когда разработчик хочет реализовать способ быстрого сохранения и доступа
        к Q&A данным.
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "TheUsage"
}
</script>

<style scoped>

</style>
