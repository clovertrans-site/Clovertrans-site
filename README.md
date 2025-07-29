<!DOCTYPE html>
<html lang="bg">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Клоувър Транс ЕООД</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0; padding: 0;
      background: #f7f9fc;
      color: #333;
    }
    header {
      background-color: #2a8fbd;
      color: white;
      padding: 20px 40px;
      text-align: center;
    }
    header h1 {
      margin: 0;
      font-weight: 700;
    }
    nav {
      background: #145374;
      display: flex;
      justify-content: center;
      padding: 10px 0;
    }
    nav a {
      color: white;
      text-decoration: none;
      margin: 0 20px;
      font-weight: 600;
      font-size: 16px;
      transition: color 0.3s;
    }
    nav a:hover {
      color: #ffd700;
    }
    main {
      max-width: 900px;
      margin: 30px auto;
      padding: 0 20px;
    }
    section {
      margin-bottom: 40px;
    }
    h2 {
      color: #2a8fbd;
      border-bottom: 2px solid #2a8fbd;
      padding-bottom: 5px;
    }
    ul {
      list-style-type: disc;
      padding-left: 20px;
    }
    footer {
      background-color: #145374;
      color: white;
      text-align: center;
      padding: 20px 40px;
      font-size: 14px;
    }
    form label {
      display: block;
      margin-top: 15px;
      font-weight: 600;
    }
    form input, form textarea {
      width: 100%;
      padding: 8px;
      margin-top: 5px;
      border: 1px solid #ccc;
      border-radius: 4px;
      font-size: 14px;
      resize: vertical;
    }
    form button {
      margin-top: 20px;
      background-color: #2a8fbd;
      color: white;
      border: none;
      padding: 12px 20px;
      font-size: 16px;
      border-radius: 4px;
      cursor: pointer;
      transition: background-color 0.3s;
    }
    form button:hover {
      background-color: #1d5d80;
    }
    #form-message {
      margin-top: 15px;
      font-weight: 600;
    }
    #form-message.success {
      color: green;
    }
    #form-message.error {
      color: red;
    }
  </style>
</head>
<body>
  <header>
    <h1>Клоувър Транс ЕООД</h1>
    <p>Международен транспорт и логистика - Турция до Европа</p>
  </header>
  <nav>
    <a href="#about">За нас</a>
    <a href="#services">Услуги</a>
    <a href="#contact">Контакти</a>
  </nav>
  <main>
    <section id="about">
      <h2>За Клоувър Транс</h2>
      <p>
        Клоувър Транс ЕООД е водеща компания в сферата на международния транспорт и логистика. 
        Специализираме се в превози от Турция към Европа с модерни камиони и надеждна складова база.
      </p>
    </section>

    <section id="services">
      <h2>Нашите услуги</h2>
      <ul>
        <li>Международен товарен транспорт</li>
        <li>Логистични решения и складова услуга</li>
        <li>Проследяване на пратки в реално време</li>
        <li>Персонализирани транспортни оферти</li>
      </ul>
    </section>

    <section id="contact">
      <h2>Свържете се с нас</h2>
      <p>Email: <a href="mailto:clovertransltd@gmail.com">clovertransltd@gmail.com</a></p>
      <p>Телефони: +359 87 853 0474, +359 878 477 677</p>

      <form id="contact-form" action="#" method="post" novalidate>
        <label for="name">Име:</label>
        <input type="text" id="name" name="name" required />

        <label for="email">Email:</label>
        <input type="email" id="email" name="email" required />

        <label for="message">Съобщение:</label>
        <textarea id="message" name="message" rows="5" required></textarea>

        <button type="submit">Изпрати</button>

        <div id="form-message"></div>
      </form>
    </section>
  </main>
  <footer>
    &copy; 2025 Клоувър Транс ЕООД. Всички права запазени.
  </footer>

  <script>
    document.getElementById('contact-form').addEventListener('submit', function(event) {
      event.preventDefault();

      const name = this.name.value.trim();
      const email = this.email.value.trim();
      const message = this.message.value.trim();
      const formMessage = document.getElementById('form-message');

      // Основна валидация
      if (!name || !email || !message) {
        formMessage.textContent = 'Моля, попълнете всички полета.';
        formMessage.className = 'error';
        return;
      }

      // Проверка за валиден email (опростена)
      const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
      if (!emailPattern.test(email)) {
        formMessage.textContent = 'Моля, въведете валиден email.';
        formMessage.className = 'error';
        return;
      }

      // Тук можеш да добавиш изпращане към сървър с fetch/AJAX

      // За демонстрация показваме съобщение за успех и изчистваме формата
      formMessage.textContent = 'Благодарим Ви! Вашето съобщение беше изпратено.';
      formMessage.className = 'success';

      this.reset();
    });
  </script>
</body>
</html>