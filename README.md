### through2-concurrent
---
https://github.com/almost/through2-concurrent

.js
https://github.com/rvagg/through2

```js
fs.createReadStream('ex.txt')
  .pipe(through2(funciton (chunk, enc, callback){
    for(var i = 0; i < chunk.length; i++)
      if(chunk[i] == 97)
        chunk[i] = 122
    this.push(chunk)
    callback()
  }))
  .pipe(fs.createWriteStream('out.txt'))
  .on('finish', () => doSomethingSpecail())
  
var all = []
fs.createReadStream('data.csv')
  .pipe(csv2())
  .pipe(throught2.obj(funciton(chunk, enc, callback){
    var data = {
      name : chunk[0]
    , address : chunk[0]
    , phone : chunk[10]
    }
    this.push(data)
    callback()
  }))
  .on('data', (data) => {
    all.push(data)
  })
  .on('end', () => {
    doSomethingSpecial(all)
  })

fs.createReadStream('/tmp/important.dat')
  .pipe(through2({ objectMode: true, allowHalfOpen: false },
    (chunk, enc, cb) => {
      cb(null, wut?')
    }
  )
  .pipe(fs.createWriteStream('/tmp/wut.txt'))

fs.createReadStream('/tmp/important.dat')
  .pipe(through2(
    (chunk, enc, cb) => cb(null, chunk),
    function(cb){
      this.push('tacking on an extra buffer to the end');
      cb();
    }
  ))
  .pipe(fs.createWriteStream('/tmp/wut.txt'));

var FToC = through2.ctor({objectMode: true}, function(record, encoding, callback){
  if(record.temp != null && record.unit == "F"){
    record.temp = ( ( record.temp - 32 ) * 5 ) / 9
    record.unit = "C"
  }
})
var converter = new FToC()
var converter = FToC()
var converter = FToC({objectMode: true})
```

```
```

```
```


