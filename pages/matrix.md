---
layout: default
title: Documentation - Matrices
permalink: ./docs/matrices/
---

## Matrices

### Creating a matrix

When creating a new matrix we have to import it first then we create a new matrix.

```js

  import Matrix2 from '../../../Library/Math/Matrix2.js'

  const firstMatrix = [
    1, 6,
    3, 8,
  ]

  const matrix = new Matrix2(matrixArray)

```


The code below is what happens when you create a new matrix.

```js

  constructor(items){
    this.items = items || [
      0, 0,
      0, 0,
    ]
  }

```

### Matrix operations
You can do multiple changes to the matrix, here is what to call them.

```js

  matrix.add(secondMatrix)

```

**add(m2)**

When you call the **add()** function the function adds 2 vectors together.

```js

  add(secondMatrix)
  {
    const firstMatrix = this.items
    this.items = [
      firstMatrix[0] + secondMatrix[0], firstMatrix[1] + secondMatrix[1],
      firstMatrix[2] + secondMatrix[2], firstMatrix[3] + secondMatrix[3]
    ]
  }

```

**sub(m2)**

The **sub()** function subtracts 2 matrices.

```js

  sub(secondMatrix)
  {
    const firstMatrix = this.items
    this.items = [
      firstMatrix[0] - secondMatrix[0], firstMatrix[1] - secondMatrix[1],
      firstMatrix[2] - secondMatrix[2], firstMatrix[3] - secondMatrix[3]
    ]
  }

```

**mul(m2)**

When we call this function we get the product of 2 matrices.

```js

  mul(secondMatrix)
  {
    const firstMatrix = this.items
    const resultMatrix = []
    resultMatrix[0] = firstMatrix[0] * secondMatrix[0] + firstMatrix[1] * secondMatrix[2]
    resultMatrix[1] = firstMatrix[0] * secondMatrix[1] + firstMatrix[1] * secondMatrix[3]
    resultMatrix[2] = firstMatrix[2] * secondMatrix[0] + firstMatrix[3] * secondMatrix[2]
    resultMatrix[3] = firstMatrix[2] * secondMatrix[1] + firstMatrix[3] * secondMatrix[3]

    this.items = resultMatrix
  }
  
```

**rot(α)**

This function rotates the matrix.

```js

  rot(α) {
    α *= Math.PI / 180
    const cos = Math.cos(α)
    const sin = Math.sin(α)
    const firstMatrix = this.items
    const rotationMatrix = [
        cos, -sin,
        sin, cos,
    ]
    this.items = rotationMatrix
    this.mul(firstMatrix);
  }

```




