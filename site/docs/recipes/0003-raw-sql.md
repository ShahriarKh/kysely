# Raw SQL

You can execute raw SQL strings and pass raw SQL snippets to pretty much any method or function
using the [sql template tag](https://kysely-org.github.io/kysely-apidoc/interfaces/Sql.html).

For example, you can do:

```ts
import { sql } from 'kysely'
import type { Person } from 'type-editor' // imaginary module

const query = sql<Person[]>`select * from person where id = ${id}`
```

SQL snippets can be executed by calling the execute method and passing a Kysely instance as the only argument:

```ts
const { rows: results } = await sql<Person[]>`select * from person`.execute(db)
```
