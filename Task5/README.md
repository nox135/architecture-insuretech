# REST API:
Если нам нужно получить информацию по клиенту, по его родственникам, а также по его документам, то мы сделаем 3 запроса:
1. /clients/{id} - забираем данные по клиенту: (id, name, age)
2. /clients/{id}/documents - забираем данные по документам: (id, type, number, issueDate, expiryDate)
3. /clients/{id}/relatives - забираем данные по родственникам: (id, relationType, name, age)

# GraphQL:
В случае с GraphQL мы можем забрать данные по трём сущностям за один запрос:
```
query {
  client(id: "1") {
    id
    name
    age
    documents {
      id
      type
      number
      issueDate
      expiryDate
    }
    relatives {
      id
      name
      relationType
      age
    }
  }
}
```

Также, преимущество в гибкости: при необходимости мы можем убрать из запроса любую сущность или конкретное поле,
получая только нужные данные и экономя трафик и вычислительные ресурсы сервера.