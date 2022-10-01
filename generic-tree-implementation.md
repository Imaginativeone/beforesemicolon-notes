# Generic Unordered Tree
- [What do the preceding hashtags mean?](https://github.com/tc39/proposal-class-fields)
- [Javascript Maps](https://www.w3schools.com/js/js_object_maps.asp)
- [Linked Lists](https://www.youtube.com/playlist?list=PLpWvGP6yhJUjYVMTzZIQmOHssllxAw8QY)
```
class Tree {
  // The preceding hashtags indicate PRIVATE FIELDS in the Tree Class
  // https://github.com/tc39/proposal-class-fields
  #children = new Map() // Could also be a linked list
  #parent = null;
  #id = Math.floor(Math.random() * Date.now());
  #name;
  
  constructor(name) {
    if(!name || typeof name != 'string' || !name.trim().length) {
      throw new Error('Name must be a non-empty String');
    }
    this.#name = name;
  }
  
  get name() {
    return this.#name;
  }
  
  set name(newName) {
  
    if(!newName || typeof newName != 'string' || !newName.trim().length) {
      throw new Error('Cannot change name. Name must be a non-empty String');
    }
    this.#name = newName;
  }
  
  get identifier() {
    return this.#id;
  }
  
  get children() { // In the field definitions, there's a "children" Map()
    return Array.from(this.#children.values());
  }
  
  get parentNode() {
    return this.#parent;
  }
  
  get childrenCount() { // In the field definitions, there's a "children" Map()
    return this.#children.size;
  }
}
```

```
const tree = new Tree('root');

console.log(tree.name);
console.log(tree.identifier);
console.log(tree.parentNode);
console.log(tree.childrenCount);
```

- 4,912 views  Aug 4, 2020  Simple walkthrough on how to implement a generic tree data structure in javascript. Intro to tree implementations using simple algorithms and logic.
- Next Video To Watch: 
  - File System Tree - https://youtu.be/cVTbdo17mYs
- Reference Videos
  - Linked Lists = https://youtu.be/HEPlGiiAVe4
  - Closure = https://youtu.be/sDmn6p4lRHk
  - Recursion = https://youtu.be/7oLO9iAyYIM
- timeline:
- 00:00 - Intro
- 00:23 - create a tree
- 01:11 - implement setters and getters
- 01:55 - create a child node
- 02:40 - print tree as string
- 04:01 - has child node check
- 04:25 - unique id generator
- 05:03 - get child node
- 05:33 - remove child node
- 06:28 - append child node
- 09:38 - traverse and search tree
- source code: https://github.com/beforesemicolon/tu...
- playlist: https://www.youtube.com/playlist?list...
- blog
- website = https://beforesemicolon.com/blog
- medium = https://beforesemicolon.medium.com/
- follow @:
  - Instagram = https://www.instagram.com/before_semi...
  - twitter = https://twitter.com/BeforeSemicolon
  - facebook = https://www.facebook.com/beforesemicolon
  - codepen = https://codepen.io/beforesemicolon
- All nodes contain the same information and can do the same type(s) of operations.
