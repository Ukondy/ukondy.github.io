# ukondy.github.io
<!DOCTYPE html>
<html lang="ru" xmlns:th="http://www.thymeleaf.org">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Change Profile</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        .container {
            background-color: #ffffff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            width: 400px;
        }

        h1 {
            margin-bottom: 20px;
            color: #333;
            text-align: center;
        }

        input[type="text"],
        input[type="email"],
        input[type="number"],
        input[type="password"] {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 4px;
            box-sizing: border-box;
        }

        input[type="submit"] {
            background-color: #5cb85c;
            color: white;
            padding: 10px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            width: 100%;
        }

        input[type="submit"]:hover {
            background-color: #4cae4c;
        }

        .footer {
            margin-top: 20px;
            font-size: 14px;
            color: #777;
            text-align: center;
        }

        .footer a {
            color: #5cb85c;
            text-decoration: none;
        }

        .footer a:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>
<div class="container">
    <h1>User's Profile</h1>
    <form th:action="@{/profile/admit}" th:method="POST" th:object="${client}">
        <input type="hidden" name="clientId" value="1">
        <label for="name">Name:</label>
        <input type="text" id="name" th:field="*{name}" name="name" th:value="${client.getName()}" required>
        <div style="color:darkred" th:if="${#fields.hasErrors('name')}" th:errors="*{name}"></div>

        <label for="surname">Surname:</label>
        <input type="text" id="surname" th:field="*{surname}" name="surname" th:value="${client.getSurname()}" required>
        <div style="color:darkred" th:if="${#fields.hasErrors('surname')}" th:errors="*{surname}"></div>

        <label for="age">Age:</label>
        <input type="number" id="age" th:field="*{age}" name="age" th:value="${client.getAge()}" required>
        <div style="color:darkred" th:if="${#fields.hasErrors('age')}" th:errors="*{age}"></div>

        <label for="phone">Phone:</label>
        <input type="text" id="phone" th:field="*{phone}" name="phone" th:value="${client.getPhone()}" required>
        <div style="color:darkred" th:if="${#fields.hasErrors('phone')}" th:errors="*{phone}"></div>

        <label for="email">Email:</label>
        <input type="email" id="email" th:field="*{email}" name="email" th:value="${client.getEmail()}" required>
        <div style="color:darkred" th:if="${#fields.hasErrors('email')}" th:errors="*{email}"></div>

        <label for="password">Password:</label>
        <input type="password" id="password" th:field="*{password}" name="password" th:value="${client.getPassword()}" required>
        <div style="color:darkred" th:if="${#fields.hasErrors('password')}" th:errors="*{password}"></div>

        <input type="submit" value="Save changes">
    </form>
    <div class="footer">
        <p><a href="/account">Back to profile</a></p>
    </div>
</div>
</body>
</html>
