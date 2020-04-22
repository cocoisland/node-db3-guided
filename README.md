
### Knex join
```

db('employees as e')
  .join('departments as d', 'e.department_id', 'd.id')
  .select('d.id', 'd.name', 'e.first_name', 'e.last_name', 'e.salary')

function find() {
  return db('users');
}

function findById(id) {
// first() returns the first entry in the db matching the query
  return db('users').where({ id }).first();
}

function add(user) {
  db('users').insert(user)
  .then(ids => {
    return findById(ids[0]);
  });
}


```


