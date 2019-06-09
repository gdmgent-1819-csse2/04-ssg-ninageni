---
layout: default
title: Webgl2 - Vectors
permalink: ./docs/vectors/
---

## Vectors

### Creating a vector

When creating a new vector we have to import it first then we create a new vector.

```js

  import Vector2 from '../../../Library/Math/Vector2.js'

  const firstVector = new Vector2(3, 6)
  
```

The code below is what happens when you create a new vector.

```js

  constructor(x, y) 
  {
    this.x = Number(x) || 0
    this.y = Number(y) || 0
  }

```

### Vector operations
You can do multiple changes to the vector, here is how to call them.

```js

  firstVector.add(secondVector)
  firstVector.scalar(2)

```

**add(v2)**

When you call the **add()** function the function adds 2 vectors together.

```js

  add(secondVector) 
  {
    this.x += secondVector.x
    this.y += secondVector.y
  }

```

**sub(v2)**

The **sub()** function subtracts 2 vectors.

```js

  sub(secondVector) 
  {
    this.x -= secondVector.x
    this.y -= secondVector.y
  }

```

**scalar(a)**

This function multiplies a vector by a given number.

```js

  scalar(scalar) 
  {
    this.x *= scalar
    this.y *= scalar
  }

```

**dot(v2)**

When we call this function we get the product of 2 vectors.

```js

  dot(secondVector) {
    return this.x * secondVector.x + this.y * secondVector.y
  }

```

**norm()**

This function gives us the length of the vector.

```js

  norm() 
  {
    return Math.sqrt(Math.pow(this.x, 2) + Math.pow(this.y, 2));
  }

```

**rot(α)**

This function rotates the vector.

```js

  rot(α) {
    const matrix = new Matrix2([
      this.x, 0, 
      this.y, 0
    ])
    matrix.rot(α)
    console.log(matrix)
    this.x = matrix.items[0]
    this.y = matrix.items[2]
  }
  
```




