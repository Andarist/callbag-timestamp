# callbag-timestamp

Callbag operator that attaches a timestamp to each emitted value.

## Example

```js
import forEach from 'callbag-for-each'
import pipe from 'callbag-pipe'
import take from 'callbag-take'
import timer from 'callbag-timer'
import timestamp from 'callbag-timestamp'

pipe(
  timer(0, 1000),
  timestamp,
  take(5),
  forEach(timestamped => {
    // will log:
    // [1378690776351, 0]
    // [1378690777313, 1]
    // [1378690778316, 2]
    // [1378690779317, 3]
    // [1378690780319, 4]
    console.log(timestamped)
  }),
)
```
