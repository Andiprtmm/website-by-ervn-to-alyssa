<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- ganti nama/judul website -->
    <title>Website by ERVN for U</title>
    <style>
      body {
        /* ganti background website */
        background-image: url(https://img.freepik.com/premium-photo/defocused-lights-form-heart-black-background_607094-211.jpg);
      }
    </style>
    <link
      rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css"
    />
  </head>

  <body class="justify-center flex">
    <main
      class="bg-white rounded mt-24 p-8 shadow-lg shadow-red-200 animate__animated animate__backInDown"
    >
      <!-- ganti gambar awal -->
      <img
        class="cat-img"
        src="https://media.tenor.com/lXZMsSVmKrIAAAAi/pout-cat.gif"
        alt="Picture of a cat"
        width="200"
      />
      <div class="border-b mt-2 border-2"></div>
      <div class="lh-1 text-center mt-4">
        <!-- ganti nama -->
        <h2 class="title text-red-400 text-xl font-semibold">
          Alyssaaaa,
        </h2>
        <!-- ganti pertanyaan -->
        <p class="title question fs-1 text-2xl font-bold text-gray-700">Udah yahh jadi jahat nyaa😖</p>
      </div>
      <div class="buttons mt-5 flex justify-around">
        <!-- ganti tulisan tombol -->
        <button
          type="button"
          class="btn-yes bg-green-500 rounded text-white text-3xl px-2 pt-1 pb-2 animate__pulse animate__animated animate__infinite"
        >
          yes
        </button>
        <button
          type="button"
          class="btn-no bg-red-500 rounded text-white text-2xl px-2 pt-1 pb-2"
        >
          no
        </button>
      </div>
      <div class="numbers hidden mt-5 flex justify-center">
        <!-- ganti link -->
        <a
          href="https://wa.me/6285806334483"
          type="button"
          class="bg-green-500 text-white py-1 px-2 rounded btn-yes w-100 text-xl font-bold"
        >
          <!-- ganti tulisan tombol link -->
          yeyy, Cepetan bales aku angenn😡</a
        >
      </div>
    </main>

    <script>
      const titleElement = document.querySelector(".title");
      const buttonsContainer = document.querySelector(".buttons");
      const numberContainer = document.querySelector(".numbers");
      const yesButton = document.querySelector(".btn-yes");
      const noButton = document.querySelector(".btn-no");
      const catImg = document.querySelector(".cat-img");
      const title = document.querySelector(".title");
      const question = document.querySelector(".question");

      // jumlah gambar
      const MAX_IMAGES = 5;

      let play = true;
      let count = 0;

      // ganti gambar pake link gif yang kalian mau
      let listGambar = [
        "https://media.tenor.com/BrSgk0WZhTcAAAAi/pouty-bunny-bunny.gif",
        "https://media.tenor.com/_mIjQPNFrBAAAAAi/angry.gif",
        "https://media.tenor.com/qL8VaSflxn0AAAAj/choco.gif",
        "https://media.tenor.com/FPzGMNfFGnYAAAAi/cute-cat.gif",
        "https://media1.tenor.com/m/pjBtpAFSnmgAAAAC/peach-goma-peach-and-goma.gif",

        // gambar kalo dijawab ya
        "https://media.tenor.com/8tgG_KyJqqwAAAAi/happy-happy-happy-happy.gif",
      ];

      yesButton.addEventListener("click", handleYesClick);

      noButton.addEventListener("click", function () {
        title.classList.add("hidden");
        question.classList.add("hidden");
        if (play) {
          count++;
          const imageIndex = Math.min(count, MAX_IMAGES);
          changeImage(imageIndex);
          updateNoButtonText();
          if (count === MAX_IMAGES) {
            play = false;
          }
        }
      });

      function handleYesClick() {
        buttonsContainer.classList.add("hidden");
        title.classList.add("hidden");
        question.classList.add("hidden");
        numberContainer.classList.remove("hidden");
        changeImage(6);
      }

      // ganti kata-kata kalo ditolak
      function generateMessage(count) {
        const messages = ["no", "kiyutt?", "klik yes?", "yes woi kiyutt", "huftt...", "eror wkwk"];

        const messageIndex = Math.min(count, messages.length - 1);
        return messages[messageIndex];
      }

      function changeImage(imageIndex) {
        catImg.src = `${listGambar[imageIndex - 1]}`;
      }

      function updateNoButtonText() {
        noButton.innerHTML = generateMessage(count);
      }
    </script>
  </body>
</html>
