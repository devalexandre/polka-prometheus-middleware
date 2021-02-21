# polka-prometheus-middleware

## Install
```
npm  i -S polka-prometheus-middleware
```


## How To

```.javascript

const polka = require('polka-prometheus-middleware')

const app  = polka({
    metricsPath: '/metrics',
    collectDefaultMetrics: true,
    requestDurationBuckets: [0.1, 0.5, 1, 1.5]
})

app
    .get('/users/:id', (req, res) => {
        console.log(`~> Hello, ${req.hello}`);
        res.end(`User: ${req.params.id}`);
    })
    .listen(3000, err => {
        if (err) throw err;
        console.log(`> Running on localhost:3000`);
    });
```