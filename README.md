# mity

> Yet another event emitter

### INSTALL AND USE mity

mity is registered as an Node package with NPM. You can install the latest version of mity with the command:


```js
npm install mity
```

If you want to use mity you can import it with:

```js
const Mity = require('mity');
```

### DEFINING mity CHANNELS

```js
const UsersChannel = Mitter.channel('users');
const NotificationsChannel = Mitter.channel('notifications');
```

### USING mity CHANNELS

```js
UsersChannel
  .suscribe({
    fetched: (users) => console.log('Users fetched:', users),
    error: (error) => NotificationsChannel.dispatch('error', error)
  })
  .suscribeOnce({
    fetch: () => console.log('Fetching users...')
  });
```

```js
UsersChannel.unsuscribe('fetched');
```

```js
UsersChannel.dispatch('fetch');
```


## License

[MIT License](https://opensource.org/licenses/MIT) © [Rubén Moya](http://rubenmoya.com/)
