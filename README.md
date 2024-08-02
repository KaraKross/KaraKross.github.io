# KaraKross.github.io
document.addEventListener('DOMContentLoaded', function () {
    // Масив об'єктів з шляхами до картинок та відповідним текстом
    const imageData = [
        { src: 'img/beautifullEyes.gif', text: 'Для мого Коханого Назарчика' },
        { src: 'img/avaValerii.jpg', text: 'Лапуська моя' },
        { src: 'img/loveyouandme.gif', text: 'Знай що я дуже тебе кохаю!' },
        { src: 'img/say.gif', text: 'більше ніж ти мене.. повторюю' },

        { src: 'img/eat.gif', text: 'ЛЮблю як ти нямкаєш' },
        { src: 'img/eatnight.gif', text: 'В 11 годин теж нямкаєш' },
        { src: 'img/eatall.gif', text: 'за смачненькі улюблені страви душу продасиш' },
        { src: 'img/bathe.gif', text: 'ти миєшся як миле кошенятко' },
        { src: 'img/worknight.gif', text: 'часто ти довго працюєш бо заробляєш грошики' },
        { src: 'img/drive.gif', text: 'це ти на машиньці бібікаєш' },

        { src: 'img/massageMe.gif', text: 'ти робиш файний масажик я так не вмію!' },
        { src: 'img/kittysleep.gif', text: 'Любусь як ти спиш це так мило!' },

        { src: 'img/bedtogether.gif', text: 'шкода що ми зараз менше проводимо разом часу' },

        { src: 'img/cry.gif', text: 'дуже сумуємо коли одне одного не бачимо' },
        { src: 'img/jumpToMeOnHeads.gif', text: 'а це коли зустрілися після розлуки' },
        { src: 'img/hisbest.gif', text: 'а це я коли ти зробив комплімент' },
        { src: 'img/thank.gif', text: 'дякую тобі що ти в мене є' },
        
        { src: 'img/angry.gif', text: 'ти буваєш інколи злюкаєшся' },
        { src: 'img/sad.gif', text: 'а це я сумую бо ти злюкаєшся' },
        { src: 'img/funny.gif', text: 'але в основному ти милий та добрий' },
        { src: 'img/clever.gif', text: 'і не сперечайся!' },
        
        { src: 'img/glow.gif', text: 'люблю коли ти посміхаєшся та світишся від щастя' },
        
        
        { src: 'img/workoff.gif', text: 'а це я коли ти сказав що йдеш додому ти допрацював' },
        { src: 'img/rejoice.gif', text: 'ти радієш коли я тебе похвалила' },
        
        { src: 'img/bigbelly.gif', text: 'а це я гладжу твоє пузіко' },
        { src: 'img/dance.gif', text: 'я хочу якось з тобою  потанцювати' },
        { src: 'img/beautifullyou.gif', text: 'ти у красунчик' },

        { src: 'img/lovemykitty.gif', text: 'я щаслива що ти є' },
        { src: 'img/end.gif', text: 'дуже сумую Назарчику❤️' },
        

    ];

    let currentIndex = 0; // Початковий індекс

  const imageElement = document.getElementById('currentImage');
  const imageTextElement = document.getElementById('imageText');
  const imageIndicatorElement = document.getElementById('imageIndicator'); // Елемент індикатора
  const nextImageButton = document.getElementById('changeImage');
  const previousImageButton = document.getElementById('previousImage');

  function updateImageIndicator() {
    imageIndicatorElement.textContent = `${currentIndex + 1} з ${imageData.length}`; // Оновлення індикатора
  }

  function changeImage(next = true) {
    imageElement.classList.add('hidden');
    setTimeout(function() {
      if (next) {
        currentIndex = (currentIndex + 1) % imageData.length; // Наступне зображення
      } else {
        currentIndex = (currentIndex - 1 + imageData.length) % imageData.length; // Попереднє зображення
      }
      imageElement.src = imageData[currentIndex].src;
      imageTextElement.textContent = imageData[currentIndex].text; // Оновлення тексту
      imageElement.classList.remove('hidden');
      updateImageIndicator(); // Виклик оновлення індикатора
    }, 100);
  }

  nextImageButton.addEventListener('click', function() {
    changeImage(true);
  });

  previousImageButton.addEventListener('click', function() {
    changeImage(false);
  });

  updateImageIndicator(); // Початкове оновлення індикатора
});
