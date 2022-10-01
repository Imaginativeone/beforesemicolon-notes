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

- All nodes contain the same information and can do the same type(s) of operations.
