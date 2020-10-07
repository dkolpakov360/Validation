# 2. Валидация с помощью исключений
a. Создайте простую html-страницу с веб-формой, в форме должны быть поля name - имя, age -
возраст, email - email.

b. При отправке формы если валидация пройдена, то должно быть выведено сообщение об
успешном изменении, при ошибке валидации - должна быть выведена соответствующая ошибка.

c. Код для обработки запроса формы должен выглядеть так:

$success = false;
if (! empty($_POST)) {
try {
$success = (new UserFormValidator())->validate($_POST);
} catch (\Exception $e) {
$error = $e->getMessage();
}
}

d. Создайте класс UserFormValidator - реализуйте метод validate.

e. Требования к валидации:

- имя должно быть не пустым

- возраст должен быть не менее 18 лет

- email - должен быть заполнен и соответствовать формату email
