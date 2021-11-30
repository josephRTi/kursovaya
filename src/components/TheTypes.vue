<template>
  <div class="slider">
    <div class="container with-nav">
      <div class="card-flex">
        <div class="item2">
          <h3>Key-value stores / Хранилища типа «ключ-значение»</h3>
          <p>Отсутствие схемы в базах данных «ключ-значение», например, Riak, — это как раз то, что вам
            нужно для хранения данных. Ключ может быть синтетическим или автосгенерированным, а значение может быть
            представлено строкой, JSON, блобом (BLOB, Binary Large Object, большой двоичный объект) и т.д.
          </p>
        </div>
        <div class="item2-img">
          <img class="responsive usage-img" src="https://dv-website.s3.amazonaws.com/uploads/2018/09/kvd-pic1.png"
               alt="">
        </div>
      </div>

      <div class="card-flex">
        <div class="item2">
          <h3>Документоориентированная база данных</h3>
          <p>Данные, представленные парами ключ-значение, сжимаются как хранилище документов схожим с хранилищем
            «ключ-значение» образом, с той лишь разницей, что хранимые значения (документы) имеют определённую структуру
            и
            кодировку данных. XML, JSON и BSON — некоторые из стандартных распространённых кодировок.</p>
        </div>

        <div class="item2-img">
          <img src="https://studref.com/htm/img/15/6644/35.png" alt="" class="responsive usage-img">
        </div>
      </div>
      <div class="card-flex">
        <div class="item2">
          <h3>Колоночная база данных</h3>
          <p>В колоночных NoSQL базах данных данные хранятся в ячейках, сгруппированных в колонки, а не в строки данных.
            Колонки логически группируются в колоночные семейства. Колоночные семейства могут состоять из практически
            неограниченного количества колонок, которые могут создаваться во время работы программы или во время
            определения схемы. Чтение и запись происходит с использованием колонок, а не строк.</p>
        </div>
        <div class="item2-img">
          <img
              src="https://0x1.tv/img_auth.php/3/30/Колоночные_БД_на_примере_Parquet_%28Леонид_Блохин%2C_SECON-2017%29%21.jpg"
              alt="" class="responsive usage-img">
        </div>
      </div>
      <div class="card-flex">
        <div class="item2">
          <h3>Графовая база данных</h3>
          <p>В графовой базе данных вы не найдёте строгого формата SQL или представления таблиц и колонок, вместо этого
            используется гибкое графическое представление, которое идеально подходит для решения проблем
            масштабируемости.
            Графовые структуры используются вместе с рёбрами, узлами и свойствами, что обеспечивает безиндексную
            смежность. При использовании графового хранилища данные могут быть легко преобразованы из одной модели в
            другую.</p>
        </div>
        <div class="item2-img">
          <img src="https://tproger.ru/s3/uploads/2018/10/graf-2.jpg" alt="" class="responsive usage-img">
        </div>
      </div>
    </div>
    <a class="prev" @click="minusSlide">&#10094;</a>
    <a class="next" @click="plusSlide">&#10095;</a>
  </div>
  <div class="container card">
    <div class="slider-dots">
      <span class="slider-dots_item" onclick="currentSlide(1)"></span>
      <span class="slider-dots_item" onclick="currentSlide(2)"></span>
      <span class="slider-dots_item" onclick="currentSlide(3)"></span>
      <span class="slider-dots_item" onclick="currentSlide(4)"></span>
    </div>
  </div>
</template>

<script>

export default {
  name: "TheTypes",
  data() {
    return {
      slideIndex: 1,
      slides: [],
      dots: []
    }
  },
  mounted() {
    this.slides = document.getElementsByClassName("card-flex");
    this.dots = document.getElementsByClassName("slider-dots_item")
    this.showSlides(this.slideIndex);
  },
  methods: {
    plusSlide() {
      this.showSlides(this.slideIndex += 1);
    },

    /* Функция уменьшяет индекс на 1, показывает предыдущий слайд*/
    minusSlide() {
      this.showSlides(this.slideIndex -= 1);
    },

    /* Устанавливает текущий слайд */
    currentSlide(n) {
      this.showSlides(this.slideIndex = n);
    },

    /* Основная функция слайдера */
    showSlides(n) {
      var i;
      // var slides = document.getElementsByClassName("item");
      // var dots = document.getElementsByClassName("slider-dots_item");
      if (n > this.slides.length) {
        this.slideIndex = 1
      }
      if (n < 1) {
        this.slideIndex = this.slides.length
      }
      for (i = 0; i < this.slides.length; i++) {
        this.slides[i].style.display = "none";
      }
      for (i = 0; i < this.dots.length; i++) {
        this.dots[i].className = this.dots[i].className.replace(" active", "");
      }
      this.slides[this.slideIndex - 1].style.display = "flex";
      this.dots[this.slideIndex - 1].className += " active";
    }

  }
}

</script>

<style scoped>
/* Собственно сам слайдер */
.slider {
  max-width: 100%;
  position: relative;
  margin: auto;
  margin-bottom: 15px;
}

/* Картинка мастабируется по отношению к родительскому элементу */
.slider .item img {
  object-fit: cover;
  width: 100%;
  height: 300px;
  border: none !important;
  box-shadow: none !important;
}

/* Кнопки вперед и назад */
.slider .prev, .slider .next {
  cursor: pointer;
  position: absolute;
  top: 0;
  top: 50%;
  width: 25px;
  margin-top: -22px;
  padding: 16px;
  color: white;
  font-weight: bold;
  font-size: 18px;
  transition: 0.6s ease;
  border-radius: 0 3px 3px 0;
  background-color: rgba(0, 0, 0, 0.4);
}

.slider .next {
  right: 0;
  border-radius: 3px 0 0 3px;
  background-color: rgba(0, 0, 0, 0.4);
}

/* При наведении на кнопки добавляем фон кнопок */
.slider .prev:hover,
.slider .next:hover {
  background-color: rgba(0, 0, 0, 0.8);
}

/* Заголовок слайда */
.slideText {
  position: absolute;
  color: #fff;
  font-size: 35px;
  /* Выравнивание текста по горизонтали и по вертикали*/
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  /* Тень*/
  text-shadow: 1px 1px 1px #000, 0 0 1em #000;
}

/* Кружочки */
.slider-dots {
  text-align: center;
}

.slider-dots_item {
  cursor: pointer;
  height: 12px;
  width: 12px;
  margin: 0 2px;
  background-color: #ddd;
  border-radius: 50%;
  display: inline-block;
  transition: background-color 0.6s ease;
}

.active,
.slider-dots_item:hover {
  background-color: #aaa;
}

/* Анимация слайдов */
.slider .item {
  -webkit-animation-name: fade;
  -webkit-animation-duration: 1.5s;
  animation-name: fade;
  animation-duration: 1.5s;
}

@-webkit-keyframes fade {
  from {
    opacity: .4
  }
  to {
    opacity: 1
  }
}

@keyframes fade {
  from {
    opacity: .4
  }
  to {
    opacity: 1
  }
}

</style>
