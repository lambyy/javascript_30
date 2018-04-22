# JS Array Methods

`Array.prototype.filter(fn)` - returns new array with only entries that the testing fn returned true, otherwise []

`Array.prototype.map(fn)` - returns new array with elements being the return value of the fn called with every element in original array

`Array.prototype.sort()` - sorts by converting adjacent elements to strings & comparing unicode

`Array.prototype.sort(fn)` - sorts adjacent elements a, b in array by return values 0, 1 or -1 (also works with `true`/`false`)

`Array.prototype.reduce(fn, initialValue)` - similar to Ruby reduce, fn takes accumulator & current value of array, if no initialValue given, defaults to first value in array

`Array.prototype.some(fn)` - checks if at least one thing in array returns true when passed to fn

`Array.prototype.every(fn)` - checks if all things in array return true when passed to fn

`Array.prototype.find()` - similar to `#filter`, but returns only the first matching element

`Array.prototype.findIndex(fn)` - returns the index in the array of the first element satisfying test fn, otherwise -1

`Array.prototype.indexOf(searchValue)` - returns index of first element in the array matching `searchValue`, uses strict equality (`===`) to compare

`Array.prototype.includes(searchValue)` - returns `true` or `false` whether array includes `searchValue`

`Array.prototype.slice(startIdx, endIdx)`
  - returns shallow copy of some portion of original array starting from `startIdx` & up to not including `endIdx`
  - if `startIdx` is undefined, `#slice` begins from index 0
  - if `startIdx` is greater than array length, return []
  - if `endIdx` is undefined or greater than array length, `#slice` extracts to end of array
  - if negative indices, indicates offset from the end
  ```
    let arr = [1, 2, 3, 4];

    arr.slice(1, 3);      // [2, 3]
    arr.slice(-1);        // [4]
    arr.slice(-3, -1);    // [2, 3]
  ```

`Array.prototype.splice(startIdx, deleteCount, ...items)`
  - changes contents of array by removing existing element and/or adding new elements
  - `startIdx` indicates index at which to start changing array, if greater than array length, will be set to array length, if negative, indicates offset from the end
  - `deleteCount` is integer indicating number of existing elements to remove, if omited or greater than `array.length - startIdx` all elements from `startIdx` to end of array removed, if 0 or nega(`[1, 2, 3, 4].slice(1, 3) === []` )tive, no elements removed
  - `items` are comma separated arguments indicating new elements to add to array
  - return value of `#splice` is array of the deleted elements
  ```
    let arr = [1, 2, 3, 4];

    arr.splice(1, 2);         // arr becomes [1, 4]
    arr.splice(0, 0, 5, 6);   // arr becomes [5, 6, 1, 4]
    arr.splice(2, 1, 7);      // arr becomes [5, 6, 7, 4]
    arr.splice(0);            // arr becomes []
  ```

For additional details & examples, consult:

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array

Note: some of these methods are the same or work very similarly to their `String` equivalents
