# Tailwind UI

It's completely up to you if you want to follow along and type out the HTML and Tailwind classes for this project. If you do not, just copy the HTML below.

It is pretty simple. We are using the `Poppins` font. I added a custom Tailwind object in the head to initialize the font.

We set the `error`, `spinner` and `results` classes to `hidden` by default. We will show them when needed.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;700&display=swap"
      rel="stylesheet"
    />
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="js/script.js" defer></script>
    <script>
      tailwind.config = {
        theme: {
          extend: {
            fontFamily: {
              sans: ['poppins', 'sans-serif'],
            },
          },
        },
      };
    </script>
    <title>Loan Calculator</title>
  </head>
  <body class="bg-blue-100 px-5 relative h-full overflow-hidden">
    <!-- Alert Box -->
    <div
      id="error"
      class="absolute bottom-10 left-1/2 bg-red-600 text-white p-5 rounded-xl shadow-xl border-2 border-white text-center text-2xl transform -translate-x-1/2 translate-y-[-1000px] transition"
    >
      This is an error
    </div>

    <div class="max-w-3xl m-auto mt-20 bg-white rounded-xl shadow-xl">
      <header class="bg-slate-500 py-10 rounded-t-xl">
        <h1 class="text-3xl text-center text-white">Loan Calculator</h1>
      </header>
      <main class="p-10">
        <form id="loan-form">
          <div class="my-4">
            <label
              for="loan-amount"
              class="inline-block mb-2 text-xl text-gray-500"
              >Loan Amount $</label
            >
            <input
              type="number"
              id="loan-amount"
              class="border-2 rounded-lg p-2 w-full focus:outline-line focus:ring-2 focus:ring-blue-200 focus:border-transparent"
              placeholder="5000"
            />
          </div>

          <div class="my-4">
            <label
              for="loan-interest"
              class="inline-block mb-2 text-xl text-gray-500"
              >Loan Interest %</label
            >
            <input
              type="number"
              id="loan-interest"
              class="border-2 rounded-lg p-2 w-full focus:outline-line focus:ring-2 focus:ring-blue-200 focus:border-transparent"
              placeholder="3"
            />
          </div>

          <div class="my-4">
            <label
              for="loan-years"
              class="inline-block mb-2 text-xl text-gray-500"
              >Years To Pay</label
            >
            <input
              type="number"
              id="loan-years"
              class="border-2 rounded-lg p-2 w-full focus:outline-line focus:ring-2 focus:ring-blue-200 focus:border-transparent"
              placeholder="2"
            />
          </div>

          <div class="my-7">
            <button
              class="bg-slate-500 text-white px-4 py-3 w-full rounded-lg hover:bg-slate-600"
            >
              Calculate
            </button>
          </div>
        </form>

        <section>
          <img
            src="images/loading.gif"
            alt=""
            id="spinner"
            class="hidden m-auto"
          />

          <div id="loan-results" class="hidden">
            <h2 class="text-2xl text-center text-gray-500 mb-4">Results</h2>

            <div class="flex justify-between mb-4 bg-gray-100 p-3 rounded-lg">
              <span>Monthy Payment</span>
              <span id="monthly-result">$5000</span>
            </div>

            <div class="flex justify-between mb-4 bg-gray-100 p-3 rounded-lg">
              <span>Total Payment</span>
              <span id="payment-result">$500000</span>
            </div>

            <div class="flex justify-between mb-4 bg-gray-100 p-3 rounded-lg">
              <span>Total Interest</span>
              <span id="interest-result">$2000</span>
            </div>
          </div>
        </section>
      </main>
    </div>
  </body>
</html>
```
