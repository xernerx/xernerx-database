# xernerx-database

An extension for the xernerx framework

## Setup

```js
this.loadExtensions({
	extensions: [
		new XernerxDatabase(this, {
			// "this" being the client.
			builder: './build', // Path to where to look for the database builders.
		}),
	],
});
```

## Builder

This is a very early version so I'd recommend using every option in this example.

```js
import { DatabaseBuilder, Sequelize as S } from 'xernerx-database';

export default class UserDatabase extends DatabaseBuilder {
	constructor() {
		super('Users', {
			name: 'users',
			database: 'database',
			username: 'username',
			password: 'password',
			host: 'localhost',
			logging: false,
			storage: 'data/database',
		});

		this.structure = {
			name: {
				value: S.STRING,
				unique: true,
			},
			nickname: S.STRING,
		};
	}
}
```

The builder is a lot like a command builder.
