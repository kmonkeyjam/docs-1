---
id: js-timing-events
title: JavaScript timing events
---

Transposit operations can leverage canonical [JavaScript Timing Events](https://www.w3schools.com/js/js_timing.asp).

## setTimeout(function, milliseconds)

Executes a function after waiting a specified number of milliseconds.

| Argument | Type |  |
| :--- | :--- | :--- |
| function | Function | the function to execute |
| milliseconds | Number | the number of milliseconds to wait before executing the function |

**Returns** (String): Returns a UUID string representing the ID of the timer that is set. Use this value with the `clearTimeout()` method to cancel the timer.

**Examples**

```javascript
setTimeout(() => {
  api.log("This function executes roughly 4000ms later");
}, 4000);
// => "832b1223-8824-4392-9a46-0eb60d3e0cb6"
```

## clearTimeout(id_of_settimeout)

Clears a timer set with the `setTimeout()` method.

| Argument | Type |  |
| :--- | :--- | :--- |
| id_of_settimeout | String | the ID value of the timer returned by the `setTimeout()` method |

**Returns** (void): No return value.

**Example**

```javascript
const setTimeoutUuid = setTimeout(() => {
  api.log("This function will get cancelled");
}, 4000);
clearTimeout(setTimeoutUuid);
```

## setInterval(function, milliseconds)

Same as `setTimeout()`, but repeats the execution of the function continuously.

| Argument | Type |  |
| :--- | :--- | :--- |
| function | Function | the function to execute |
| milliseconds | Number | the length of the time-interval in milliseconds between each execution |

**Returns** (String): Returns a UUID string representing the ID of the timer that is set. Use this value with the `clearInterval()` method to cancel the timer.

**Examples**

```javascript
setInterval(() => {
  api.log("This function executes roughly every 1000ms");
  api.log("It does not stop until it is cancelled, or until the Transposit operation times out");
}, 1000);
// => "d705dc50-6c71-11e9-a923-1681be663d3e"
```

## clearInterval(id_of_setinterval)

Clears a timer set with the `setInterval()` method.

| Argument | Type |  |
| :--- | :--- | :--- |
| id_of_setinterval | String | the ID value of the timer returned by the `setInterval()` method |

**Returns** (void): No return value.

**Example**

```javascript
let count = 0;
const setIntervalUuid = setInterval(() => {
  if (count >= 3) {
    api.log("This function runs three times and then is cancelled.")
    clearInterval(setIntervalUuid);
  }
  count++;
}, 1000);
```

## setImmediate(function)

Executes a function immediately. This is equivalent to `setTimeout(function, 0)`.

| Argument | Type |  |
| :--- | :--- | :--- |
| function | Function | the function to execute |

**Returns** (String): Returns a UUID string representing the ID of the timer that is set. Use this value with the `clearImmediate()` method to cancel the timer.

**Examples**

```javascript
setImmediate(() => {
  api.log("This function executes roughly immediately");
});
// => "e0c2f842-6c74-11e9-a923-1681be663d3e"
```

## clearImmediate(id_of_setimmediate)

Clears a timer set with the `setImmediate()` method.

| Argument | Type |  |
| :--- | :--- | :--- |
| id_of_setimmediate | String | the ID value of the timer returned by the `setImmediate()` method |

**Returns** (void): No return value.

**Example**

```javascript
const setImmediateUuid = setImmediate(() => {
  api.log("This function may or may not execute depending on timing");
});
clearImmediate(setImmediateUuid);
```

## Gotchas
- The timing semantics of these functions do not exactly match the timing semantics of a conventional JavaScript event loop, like one in the browser.
- Timing is not exact; e.g. `setTimeout(function, 1000)` is not guaranteed to execute exactly 1000ms later in terms of wall-clock time.
- The `set*` and `clear*` functions cannot be mixed; e.g. this is incorrect:
    ```javascript
    const setTimeoutUuid = setTimeout(() => {
      api.log("This function will not get cancelled");
    }, 4000);
    clearInterval(setTimeoutUuid); // does not work!
    ```
- Asynchronous time is counted against Transposit operation limits; e.g. with `setTimeout(function, 10000)`, even though the function is not actively executing during the delay period, the 10000ms of delay time is still counted against the total execution time of the Transposit operation.
