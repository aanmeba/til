# CLI - `sed`

`sed` is for text substitution with `s` command following by `/`. 

```bash
$ echo "Hello sed"
$ sed 's/sed/World' # Hello World
```

```bash
sed -i 's/SEARCH_REGEX/REPLACEMENT/g' INPUT_FILE
```

- `-i` tells `sed` to edit files in place.
- `s` is the substitute command.
- `/` is a delimiter character. It can be any character but usually the slash `/` is used.
- `g` is a global replacement flag and all occurences are replaced. 

If you want to change the logo and hyperlink in the src/App.js file. You need to add option `-i` next to `sed` to specify a file you want to change. And an empty string `""` should follow the `-i` flag if you want to edit the file in-place in the MacOS version of sed. Otherwise you'll encounter `unterminated substitute pattern` error.

```javascript
import logo from './logo.svg';

function App() {
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Edit <code>src/App.js</code> and save to reload.
        </p>
        <a
          className="App-link"
          href="https://reactjs.org"
          target="_blank"
          rel="noopener noreferrer"
        >
          Learn React
        </a>
      </header>
    </div>
  );
}
```

```bash
sed -i "" 's/React/Jungah/' src/App.js
sed -i "" 's|href="https://reactjs.org"|href="https://jungah.netlify.app/"|g' src/App.
```

```javascript
function App() {
  return (
    <div className="App">
      ...
        <a
          className="App-link"
          href="https://jungah.netlify.app"
          target="_blank"
          rel="noopener noreferrer"
        >
          Learn Jungah
        </a>
      ...
    </div>
  );
}
```


### Reference:
- [What is wrong with my string substitution using sed on Mac OS X?](https://stackoverflow.com/questions/28592043/what-is-wrong-with-my-string-substitution-using-sed-on-mac-os-x)
- [How to Use sed to Find and Replace String in Files](https://linuxize.com/post/how-to-use-sed-to-find-and-replace-string-in-files/)