<template>
  <nav
    class="flex items-center py-3 w-full bg-red-600 justify-between px-[24px]"
  >
    <div class="space-x-10 flex items-center">
      <div class="space-x-4">
        <button
          class="border-2 border-white hover:border-red-200 px-3 bg-white rounded-lg py-1 text-red-500 hover:bg-red-200"
        >
          {{ mudatliTolov }}
        </button>
        <button
          class="border-2 hover:border-red-200 px-3 rounded-lg py-1 bg-transparent text-white hover:text-red-200"
        >
          {{ chegirmalar }}
        </button>
        <button
          class="border-2 border-white hover:border-red-200 px-3 bg-white rounded-lg py-1 text-red-500 hover:bg-red-200"
        >
          {{ yutuqliOyinlar }}
        </button>
      </div>
      <a href="#" class="text-white hover:text-red-200">{{ satyHaritasi }}</a>
    </div>
    <div class="flex items-center">
      <a
        class="text-2xl font-bold text-white hover:text-red-200"
        href="tel:+998712022021"
        aria-label="+998712022021"
      >
        +998 (71) 202 2021
      </a>
      <button
        class="border-2 border-white px-3 rounded-lg py-1 bg-transparent text-white hover:text-red-500 hover:bg-white mx-7"
      >
        {{ olchadaSoting }}
      </button>

      <div
        class="flex space-x-4 border-[1px] border-t-transparent border-b-transparent px-[24px] text-red-200"
      >
        <button @click="krilLotin" class="hover:text-white focus:font-bold">
          Ўзб
        </button>
        <button @click="ozbekLotin" class="hover:text-white focus:font-bold">
          O'z
        </button>
        <button @click="krilrus" class="hover:text-white focus:font-bold">
          Pyc
        </button>
      </div>
    </div>
  </nav>
  <main class="flex px-10 py-10 items-center justify-between">
    <a href="#"
      ><img
        src="https://olcha.uz/_nuxt/logo-red.e48e0ab8.svg"
        alt="olcha.uz"
        width="102"
        height="30"
    /></a>
    <div class="flex items-center space-x-10">
      <button
        class="border-2 rounded-lgatalog py-2 px-5 rounded-lg hover:text-red-600 hover:border-red-600 text-[20px] flex items-center gap-2"
      >
        <i class="bi bi-list text-[23px]"></i>{{ katalog }}
      </button>
      <div>
        <input
          type="text"
          placeholder="search"
          class="py-3 px-5 rounded-lg w-[590px] bg-slate-100 focus:bg-white"
        />
        <button
          class="px-5 py-2 border rounded-lg bg-red-600 text-white ms-[-66px]"
        >
          <i class="bi bi-search"></i>
        </button>
      </div>
    </div>
    <div class="space-x-7 flex">
      <a
        @click="taqqoslashClick"
        href="#"
        class="hover:text-red-600 items-center flex"
        style="flex-direction: column"
      >
        <i class="bi bi-text-left text-[24px]"></i>
        <p class="text-[14px]">{{ taqqoslash }}</p>
      </a>
      <a
        @click="sevimlilarClick"
        href="#"
        class="hover:text-red-600 items-center flex"
        style="flex-direction: column"
      >
        <i class="bi bi-heart text-[24px]"></i>
        <p class="text-[14px]">{{ sevimlilar }}</p>
      </a>
      <a
        @click="savatchaClick"
        href="#"
        class="hover:text-red-600 items-center flex"
        style="flex-direction: column"
      >
        <span
          class="w-[15px] h-[15px] bg-red-600 rounded-full flex justify-center items-center text-[12px] mb-[-18px] ms-[15px] text-white z-10"
          >0</span
        >
        <i class="bi bi-cart text-[24px]"></i>
        <p class="text-[14px]">{{ savatcha }}</p>
      </a>
      <div
        v-if="akk"
        class="w-[370px] py-7 border bg-white rounded-lg right-[50px] top-[27%] shadow-lg flex justify-start px-7 items-center"
        style="position: absolute; flex-direction: column"
      >
        <div class="flex justify-end" style="width: 100%">
          <button @click="orqaga">
            <i class="bi bi-x-lg"></i>
          </button>
        </div>
        <h1 class="text-2xl mt-3 mb-3">
          {{ tizimgaKirishYokiProfilYaratish }}Tizimga kirish yoki profil
          yaratish
        </h1>
        <label for="number" class="flex justify-start w-[100%]">{{
          telefonRaqam
        }}</label>
        <input
          id="number"
          type="number"
          placeholder="+998 (99) 999 9999"
          class="border rounded-lg py-2 px-3 w-[100%] mt-2"
          v-model="number"
        />
        <p class="text-red-500 text-[14px] mt-2" v-if="ogoh">
          {{ ogohlantiruvchi }}
        </p>
        <button
          @click="submib"
          class="border-red-400 border-2 rounded-lg w-[100%] py-2 text-[18px] mt-5 text-white hover:text-red-400 bg-red-400 hover:bg-white"
        >
          {{ tasdiqlash }}
        </button>
      </div>
      <a
        @click="akaunt"
        href="#"
        class="hover:text-red-600 items-center flex"
        style="flex-direction: column"
      >
        <i class="bi bi-person text-[24px]"></i>
        <p class="text-[14px]">{{ kirish }}</p>
      </a>
    </div>
  </main>
  <div v-if="numberThero" class="h-[100px]">
    <h1 class="text-5xl font-bold">
      {{ yutuqliOyinlar2 }}
    </h1>
  </div>
  <div v-if="numberOne" class="h-[400px]">
    <h1 class="text-5xl font-bold">
      {{ tavarlarningSotilishi }}
    </h1>
  </div>
  <div v-if="numberTwo" class="h-[400px]">
    <h1 class="text-5xl font-bold">
      {{ sevimliMahsulotlar }}
    </h1>
    <div class="flex items-center mt-12" style="flex-direction: column">
      <img src="https://olcha.uz/_nuxt/empty-img.3a4aef3b.png" alt="mahsulot" />
      <h2 class="text-4xl mt-3">{{ SevimliMahsulotlarYoq }}</h2>
    </div>
  </div>
  <div
    v-if="numberThera"
    class="h-[400px] flex items-center justify-center"
    style="flex-direction: column"
  >
    <i class="bi bi-cart-check-fill text-5xl"></i>

    <h1 class="text-4xl mt-8">
      {{ savatchangizBosh }}
    </h1>

    <h2 class="text-1xl mt-3">{{ LekinSizUniHarDoimToldirishingizMumkin }}</h2>
    <button
      class="border-2 border-red-600 py-[10px] px-[17px] rounded-lg mt-10 bg-red-600 text-white hover:bg-white hover:text-red-600"
    >
      {{ asosiySahifa }}
    </button>
  </div>
  <div
    class="h-[297px] w-[100%] bg-neutral-100 flex items-center justify-around"
  >
    <div class="w-[479px]">
      <h2 class="text-2xl font-bold">{{ bizningMobilIlova }}</h2>
      <div class="flex-wrap flex mt-5">
        <div
          class="m-2 ml-0 bg-green-500 w-[185px] h-[55px] flex items-center justify-center hover:bg-neutral-400 bg-white rounded-lg"
        >
          <a href="#">
            <img
              class="w-[150px] h-[50px]"
              src="https://olcha.uz/_nuxt/appstore.32a5f67a.svg"
              alt="olcha app story"
            />
          </a>
        </div>
        <div
          class="m-2 mr-0 bg-green-500 w-[185px] h-[55px] flex items-center justify-center hover:bg-neutral-400 bg-white rounded-lg"
        >
          <a href="#">
            <img
              class="w-[150px] h-[50px]"
              src="https://olcha.uz/_nuxt/googleplay.4ba35be8.svg"
              alt="olcha app story"
            />
          </a>
        </div>
        <div
          class="m-2 ml-0 bg-green-500 w-[185px] h-[55px] flex items-center justify-center hover:bg-neutral-400 bg-white rounded-lg"
        >
          <a href="#">
            <img
              class="w-[150px] h-[50px]"
              src="https://olcha.uz/_nuxt/app-gallery.879faacf.svg"
              alt="olcha app story"
            />
          </a>
        </div>
      </div>
    </div>
    <div>
      <img
        src="//olcha.uz/_nuxt/footer-img.97b6859b.png"
        alt="saasas"
        class="w-[489px] h-[264px]"
      />
    </div>
  </div>
  <footer class="footer">
    <div
      class="border flex space-x-20 px-7 justify-between bg-neutral-100 py-[50px]"
    >
      <div>
        <a href="#"
          ><img
            src="https://olcha.uz/_nuxt/logo-red.e48e0ab8.svg"
            alt="olcha.uz"
            width="102"
            height="30"
        /></a>
        <div class="space-y-3 flex flex-col mt-7">
          <p>{{ qollabQuvvatlashRaqami }}</p>
          <a
            class="text-2xl font-bold hover:text-red-500"
            href="tel:+998712022021"
            aria-label="+998712022021"
          >
            +998 (71) 202 2021
          </a>
          <p><i class="bi bi-geo-alt-fill text-red-500"></i> {{ manzil }}</p>
          <a href="#" class="hover:text-red-600"
            ><i class="bi bi-envelope"></i> info@olcha.uz</a
          >
        </div>
      </div>
      <div>
        <h2 class="mb-7 text-2xl text-red-600 font-bold">
          {{ malumot }}
        </h2>
        <div class="flex space-x-[50px]">
          <div class="space-y-3 flex flex-col">
            <a href="#" class="hover:text-gray-500">{{ bizHaqimizda }} </a>
            <a href="#" class="hover:text-gray-500">{{ boshIshOrinlari }} </a>
            <a href="#" class="hover:text-gray-500"
              >{{ tavarlarniQaytarishVaTavarlarniAlmashtirish }}
            </a>
            <a href="#" class="hover:text-gray-500"
              >{{ mudatliTolovShartlari }}
            </a>
            <a href="#" class="hover:text-gray-500">{{ yordam }} </a>
            <a href="#" class="hover:text-gray-500">{{ yetkazibBerish }} </a>
          </div>
          <div class="space-y-3 flex flex-col">
            <a href="#" class="hover:text-gray-500">{{ ekoFriendly }} </a>
            <a href="#" class="hover:text-gray-500">{{ bonusVaAksiyalar }} </a>
            <a href="#" class="hover:text-gray-500"
              >{{ tolovVaYetkazibBerish }}
            </a>
            <a href="# " class="bg-red-600 text-white">{{ OlchaSoting }} </a>
            <a href="# " class="hover:text-gray-500">{{ servisMarkazlari }} </a>
          </div>
        </div>
      </div>
      <div class="flex flex-wrap w-[300px] items-center gap-5 py-20">
        <div
          class="bg-white py-1 px-2 rounded-lg cursor-pointer hover:bg-gray-400"
        >
          <img
            src="./components/apelsin.svg"
            alt="salom"
            class="w-[70px] h-[30px]"
          />
        </div>
        <div
          class="bg-white py-1 px-2 rounded-lg cursor-pointer hover:bg-gray-400"
        >
          <img
            src="./components/uzcard.svg"
            alt="uzcard"
            class="w-[70px] h-[30px]"
          />
        </div>
        <div
          class="bg-white py-1 px-2 rounded-lg cursor-pointer hover:bg-gray-400"
        >
          <img
            src="./components/click.svg "
            alt="click"
            class="w-[70px] h-[30px]"
          />
        </div>
        <div
          class="bg-white py-1 px-2 rounded-lg cursor-pointer hover:bg-gray-400"
        >
          <img
            src="./components/payme.svg"
            alt="payme"
            class="w-[70px] h-[30px]"
          />
        </div>
        <div
          class="bg-white py-1 px-2 rounded-lg cursor-pointer hover:bg-gray-400"
        >
          <img
            src="./components/humo.svg"
            alt="humo"
            class="w-[70px] h-[30px]"
          />
        </div>
        <div
          class="bg-white py-1 px-2 rounded-lg cursor-pointer hover:bg-gray-400"
        >
          <img
            src="./components/paynet.svg"
            alt="humo"
            class="w-[70px] h-[30px]"
          />
        </div>
      </div>
    </div>
  </footer>
  <div class="flex w-[100%] py-8 px-20 justify-between bg-neutral-100">
    <div class="flex space-x-20">
      <p class="text-gray-500">© 2017-2023. 000 "Olcha store"</p>
      <a href="#" class="text-gray-500 hover:text-red-600">{{ omaviyOfera }}</a>
      <a href="#" class="text-gray-500 hover:text-red-600">{{
        maxfiylikSiyosati
      }}</a>
    </div>
    <div class="flex space-x-5">
      <a href="#" class="text-gray-500 hover:text-red-600"
        ><i class="bi bi-facebook text-[25px]"></i
      ></a>
      <a href="#" class="text-gray-500 hover:text-red-600"
        ><i class="bi bi-instagram text-[25px]"></i
      ></a>
      <a href="#" class="text-gray-500 hover:text-red-600"
        ><i class="bi bi-telegram text-[25px]"></i
      ></a>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      maxfiylikSiyosati: "Maxviylik siyosati",
      omaviyOfera: "Ommaviy oferta",
      servisMarkazlari: "Servis markazlari",
      OlchaSoting: "olcha da soting",
      tolovVaYetkazibBerish: "To'lov va yetkazib berish",
      bonusVaAksiyalar: "Bonus va aksiyalar",
      ekoFriendly: "Eco-friendly",
      yetkazibBerish: "Yetkazib berish",
      yordam: "Yordam",
      mudatliTolovShartlari: "Muddatli to'lov shartlari",
      tavarlarniQaytarishVaTavarlarniAlmashtirish:
        "To'lovni qaytarish va tovarlarni almashtirish",
      boshIshOrinlari: "Bo'sh ish o'rinlari",
      bizHaqimizda: "Biz haqimizda",
      malumot: "Ma'lumot",
      manzil: "Qozitarnov, Toshkent",
      qollabQuvvatlashRaqami: "Qo'llab-quvvatlash raqami",
      mudatliTolov: "0% Muddatli to'lov",
      chegirmalar: "Chegirmalar",
      yutuqliOyinlar: "Yutuqli o'yinlar",
      satyHaritasi: "Sayt xaritasi ",
      olchadaSoting: "Olcha da soting",
      katalog: " Katalog",
      taqqoslash: "Taqqoslash",
      sevimlilar: "Sevimlilar",
      savatcha: "Savatcha",
      kirish: "Kirish",
      sevimliMahsulotlar: "Sevimli mahsulotlar",
      SevimliMahsulotlarYoq: "Sevimli mahsulotlar yo'q",
      tavarlarningSotilishi: "Tavarlarni solishtirish",
      savatchangizBosh: "Savatchangiz bo'sh",
      LekinSizUniHarDoimToldirishingizMumkin:
        "Lekin siz uni har doim to'ldirishingiz mumkin",
      asosiySahifa: "Asosiy sahifa",
      yutuqliOyinlar2: "Yutuqli o'yinlar",
      tizimgaKirishYokiProfilYaratish: "Tizimga kirish yoki profil",
      telefonRaqam: "Telefon raqam:",
      tasdiqlash: "Tasdiqlash",
      ogohlantiruvchi: "Telefon raqami maydoni majburiy, to'ldirishingiz lozim",
      numberOne: false,
      numberTwo: false,
      numberThera: false,
      numberThero: true,
      akk: false,
      ogoh: false,
      number: "",
      bizningMobilIlova:
        "Bizning mobil ilovamiz AppGallery, App store va Google play-da",
    };
  },

  methods: {
    taqqoslashClick() {
      this.numberOne = true;
      this.numberTwo = false;
      this.numberThera = false;
      this.numberThero = false;
    },
    sevimlilarClick() {
      this.numberOne = false;
      this.numberTwo = true;
      this.numberThera = false;
      this.numberThero = false;
    },
    savatchaClick() {
      this.numberOne = false;
      this.numberTwo = false;
      this.numberThera = true;
      this.numberThero = false;
    },
    akaunt() {
      this.akk = true;
    },
    orqaga() {
      this.akk = false;
    },
    submib() {
      if (this.number === "") {
        this.ogoh = true;
      } else {
        this.ogoh = false;
        this.akk = false;
      }
    },
    ozbekLotin() {
      this.maxfiylikSiyosati = "Maxfiylik siyosati";
      this.omaviyOfera = "Ommaviy oferta";
      this.qollabQuvvatlashRaqami = "Qo'llab-quvvatlash raqami";
      this.manzil = "Qozitarnov, Toshkent";
      this.malumot = "Ma'lumot";
      this.bizHaqimizda = "Biz haqimizda";
      this.boshIshOrinlari = "Bo'sh ish o'rinlari";
      this.tavarlarniQaytarishVaTavarlarniAlmashtirish =
        "To'lovni qaytarish va tovarlarni almashtirish";
      this.mudatliTolovShartlari = "Muddatli to'lov shartlari";
      this.yordam = "Yordam";
      this.yetkazibBerish = "Yetkazib berish";
      this.bonusVaAksiyalar = "Bonus va aksiyalar";
      this.tolovVaYetkazibBerish = "To'lov va yetkazib berish";
      this.OlchaSoting = "olcha da soting";
      this.servisMarkazlari = "Servis markazlari";
      this.bizningMobilIlova =
        "Bizning mobil ilovamiz AppGallery, App store va Google play-da";
      this.mudatliTolov = "0% Muddatli to'lov";
      this.chegirmalar = "Chegirmalar";
      this.yutuqliOyinlar = "Yutuqli o'yinlar";
      this.satyHaritasi = "Sayt xaritasi";
      this.olchadaSoting = "Olcha da soting";
      this.katalog = " Katalog";
      this.taqqoslash = "Taqqoslash";
      this.sevimlilar = "Sevimlilar";
      this.savatcha = "Savatcha";
      this.kirish = "Kirish";
      this.sevimliMahsulotlar = "Sevimli mahsulotlar";
      this.SevimliMahsulotlarYoq = "Sevimli mahsulotlar yo'q";
      this.tavarlarningSotilishi = "Tavarlarni solishtirish";
      this.savatchangizBosh = "Savatchangiz bo'sh";
      this.LekinSizUniHarDoimToldirishingizMumkin =
        "Lekin siz uni har doim to'ldirishingiz mumkin";
      this.asosiySahifa = "Asosiy sahifa";
      this.yutuqliOyinlar2 = "Yutuqli o'yinlar";
      this.tizimgaKirishYokiProfilYaratish = "Tizimga kirish yoki profil";
      this.telefonRaqam = "Telefon raqam:";
      this.tasdiqlash = "Tasdiqlash";
      this.ogohlantiruvchi =
        "Telefon raqami maydoni majburiy, to'ldirishingiz lozim";
    },
    krilLotin() {
      this.maxfiylikSiyosati = "Махфийлик сиёсати";
      this.omaviyOfera = "Оммавий оферта";
      this.qollabQuvvatlashRaqami = "Қўллаб-қувватлаш рақами";
      this.manzil = "Қозитарнов, Тошкент";
      this.malumot = "Маълумот";
      this.bizHaqimizda = "Биз ҳақимизда";
      this.boshIshOrinlari = "Бўш иш ўринлари";
      this.tavarlarniQaytarishVaTavarlarniAlmashtirish =
        "Маҳсулотларини қайтариш ва алмаштириш";
      this.mudatliTolovShartlari = "Муддатли тўлов";
      this.yordam = "Ёрдам";
      this.yetkazibBerish = "Етказиб бериш";
      this.bonusVaAksiyalar = "Бонус ва акциялар";
      this.tolovVaYetkazibBerish = "Тўлов ва етказиб бериш";
      this.OlchaSoting = "olcha да сотинг";
      this.servisMarkazlari = "Сервис марказлари";
      this.mudatliTolov = "0% Муддатли тўлов";
      this.chegirmalar = "Чегирмалар";
      this.yutuqliOyinlar = "Ютуқли ўйинлар";
      this.satyHaritasi = "Сайт харитаси";
      this.olchadaSoting = "olcha да сотинг";
      this.katalog = "Каталог";
      this.taqqoslash = "Таққослаш";
      this.sevimlilar = "Севимлилар";
      this.savatcha = "Саватча";
      this.kirish = "Кириш";
      this.sevimliMahsulotlar = "Севимли маҳсулотлар";
      this.SevimliMahsulotlarYoq = "Севимли маҳсулотлар йўқ";
      this.tavarlarningSotilishi = "Товарларни солиштириш";
      this.savatchangizBosh = "Саватчангиз бўш";
      this.LekinSizUniHarDoimToldirishingizMumkin =
        "Лекин сиз уни хар доим тўлдиришингиз мумкин";
      this.asosiySahifa = "Асосий сақифага";
      this.yutuqliOyinlar2 = "Ютуқли ўйинлар";
      this.tizimgaKirishYokiProfilYaratish = "Тизимга кириш ёки профил яратиш";
      this.telefonRaqam = "Телефон рақами:";
      this.tasdiqlash = "Тасдиқлаш";
      this.ogohlantiruvchi = "Телефон рақами майдони тўлдирилиши керак";
      this.bizningMobilIlova =
        "Бизнинг мобил иловамиз AppGallery, App store ва Google play-да";
    },
    krilrus() {
      this.maxfiylikSiyosati = "Политика конфиденциальности";
      this.omaviyOfera = "Публичная оферта";
      this.qollabQuvvatlashRaqami = "Телефон поддержки";
      this.manzil = "Козитарнов, Ташкент";
      this.malumot = "Информация";
      this.bizHaqimizda = "О компании";
      this.boshIshOrinlari = "Вакансии";
      this.tavarlarniQaytarishVaTavarlarniAlmashtirish =
        "Возврат и обмен товаров";
      this.mudatliTolovShartlari = "Условия рассрочки";
      this.yordam = "Помощь";
      this.yetkazibBerish = "Доставка";
      this.bonusVaAksiyalar = "Бонусы и акции";
      this.tolovVaYetkazibBerish = "Оплата и доставка";
      this.OlchaSoting = "Продавайте на olcha";
      this.servisMarkazlari = "Сервисные центры";

      this.mudatliTolov = "0% Рассрочка";
      this.chegirmalar = "Скидки";
      this.yutuqliOyinlar = "Розыгрыши";
      this.yutuqliOyinlar2 = "Розыгрыши";
      this.satyHaritasi = "Карта сайта";
      this.olchadaSoting = "Продавайте на olcha";
      this.katalog = " Каталог";
      this.taqqoslash = "Сравнение";
      this.sevimlilar = "Избранные";
      this.savatcha = "Корзина";
      this.kirish = "Войти";
      this.sevimliMahsulotlar = "Избранные товары";
      this.SevimliMahsulotlarYoq = "Нет избранных товаров";
      this.tavarlarningSotilishi = "Сравнение товаров";
      this.savatchangizBosh = "Корзина пуста";
      this.LekinSizUniHarDoimToldirishingizMumkin =
        "Но вы всегда можете ее наполнить";
      this.asosiySahifa = "На главную";
      this.tizimgaKirishYokiProfilYaratish = "Войти или создать профиль";
      this.telefonRaqam = "Номер телефона:";
      this.tasdiqlash = "Подтвердить";
      this.ogohlantiruvchi = "Поле номер телефона обязательно для заполнения";
      this.bizningMobilIlova =
        "Наше мобильное приложение доступно в AppGallery, App store и Google play";
    },
  },
};
</script>
