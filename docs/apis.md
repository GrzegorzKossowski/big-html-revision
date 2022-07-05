<a href='../README.md' id='top' style='border: 1px solid gold; padding: 5px; color: gold'>← back to README.md</a>

# Web Worker

Webworker to js wykonywany w tle, jako oddzielny wątek, nie wpływający na jakość przetwarzania strony

https://github.com/mdn/dom-examples/tree/master/web-workers/simple-web-worker

```js
// main file
const input = document.querySelector('#input');
const output = document.querySelector('#output');
let w;

if (window.Worker) {
    if (w !== undefined) {
        // podpinamy zewnętrzny worker
        const w = new Worker('worker.js');
        input.onchange = function () {
            // wyślij dane do workera
            w.postMessage(input.value);
        };
        // pobierz dane z workera
        w.onmessage = function (e) {
            result.textContent = e.data;
        };
    }
}

const shutDown = w.terminate();
```

worker.js

```js
onmessage = function (e) {
    const result = e.data;
    if (result) {
        postMessage(`Some message + ${result}`);
    } else {
        postMessage(`No data sended`);
    }
};
```

# SSE

Server-Sent Events - sposób na nasłuchiwanie danych z serwera. Update przychodzi automatycznie.

```js
var source = new EventSource('demo_sse.php');
source.onmessage = function (event) {
    document.getElementById('result').innerHTML += event.data + '<br>';
};
```

<a href="../README.md" style="border: 1px solid gold; padding: 5px; color: gold">← back to README.md</a>

<a href="#top" style="border: 1px solid gold; padding: 5px; color: gold"> ↑ back to top</a>
