---
layout: default
title: Documentation - Clock
permalink: ./docs/clock/
---

## Clock

We are going to create a clock and this will be the end result.

```js

  updateCanvasHandler(event) {
    console.log('updateCanvas')
    this.clearData()

    this.data.positions.push(0, 0)
    this.data.colors.push(...this.colors.white)

    const vector = new Vector2(0.8, 0)
    this.data.positions.push(vector.x, vector.y)
    this.data.colors.push(...this.colors.white)

    for(let i = 0; i < 12; i++){
      vector.rot(30);
      this.data.positions.push(vector.x, vector.y)
      this.data.colors.push(...this.colors.white)
    } 

    const date = new Date()

    let seconds = date.getSeconds()
    let minutes = date.getMinutes()
    let hours = date.getHours()

    let secondsVector = new Vector2(0, 0.7)
    secondsVector.rot(seconds * -6)
    this.data.positions.push(secondsVector.x, secondsVector.y)
    this.data.colors.push(...this.colors.red)
    let minutesVector = new Vector2(0, 0.8)
    minutesVector.rot(minutes * -6)
    this.data.positions.push(minutesVector.x, minutesVector.y)
    this.data.colors.push(...this.colors.blue)
    let hoursVector = new Vector2(0, 0.6)
    hoursVector.rot(hours * -6)
    this.data.positions.push(hoursVector.x, hoursVector.y)
    this.data.colors.push(...this.colors.cyan)

    this.drawScene()
  }

```

### Creating the clock

Clear all the data first then we will create a white point in the middle.

```js

  this.clearData()

  this.data.positions.push(0, 0)
  this.data.colors.push(...this.colors.white)

```

Now we will create a new vector for the 12 points that represent the hours. We are going to rotate this vector so we get 12 points.

```js

  const v = new Vector2(0.6, 0)
  this.data.positions.push(v.x, v.y)
  this.data.colors.push(...this.colors.white)

  for(let i = 0; i < 12; i++){
    v.rot(30);
    this.data.positions.push(v.x, v.y)
    this.data.colors.push(...this.colors.white)
  } 

```

### Setting the time

First we get the time.

```js
  
  const date = new Date()

  let seconds = date.getSeconds()
  let minutes = date.getMinutes()
  let hours = date.getHours()

```

After we get the time, we convert it to vectors.

```js

  let secondsVector = new Vector2(0, 0.5)
  secondsVector.rot(seconds * -6)
  this.data.positions.push(secondsVector.x, secondsVector.y)
  this.data.colors.push(...this.colors.red)
  let minutesVector = new Vector2(0, 0.6)
  minutesVector.rot(minutes * -6)
  this.data.positions.push(minutesVector.x, minutesVector.y)
  this.data.colors.push(...this.colors.yellow)
  let hoursVector = new Vector2(0, 0.4)
  hoursVector.rot(hours * -6)
  this.data.positions.push(hoursVector.x, hoursVector.y)
  this.data.colors.push(...this.colors.green)

```

### Draw the time

Then we will put the time on the screen.

```js
  
  this.drawScene()

```

