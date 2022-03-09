# First non-repeating character

Given a string of characters, how do you find the first single (non-repeating) character in the string?

## Javascript

> Short answer using array methods

```javascript
const firstNonRepeatedCharacter = (string) => {
  const chars = string.split('');
  return chars.find((char) => chars.filter((j) => j == char).length == 1);
};
```

> Using **"for" loopings**

```javascript
const firstNonRepeatedCharacter = (string) => {
  const chars = {};
  for (var i = 0; i < string.length; i++) {
    chars[string.charAt(i)] = (chars[string.charAt(i)] || 0) + 1;
  }

  for (var i = 0; i < string.length; i++) {
    if (chars[string.charAt(i)] === 1) return string.charAt(i);
  }
};
```

> Using **"for of" loopings**

```javascript
const firstNonRepeatedCharacter = (string) => {
  const chars = string.split('');
  const charsMap = {};

  for (let char of chars) {
    charsMap[char] = (charsMap[char] || 0) + 1;
  }

  for (let char of chars) {
    if (charsMap[char] === 1) return char;
  }
};
```
