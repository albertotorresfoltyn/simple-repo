# simple repository pattern implementation for node

Technologic stack:
  - nodeJs + ecma 6
  - mongodb + mongo driver

# Features!

  - It provides a super simple interface to mongodb collections over mongodb driver

# Example:
To run the project you need to:
 ```javascript
app.get('/testall', async (request, response) => {
  try {
    let test = new generic("megaDB","prueba")
    let record = await test.create({p1:"o1",p2:"o2",p3:{o1:2}})
    let r2 = await test.read({p1:"o1"})
    for (let doc = await r2.next(); doc != null; doc = await r2.next()) {
      console.log(doc);
    }
    let r3 = await test.update("59a43779132f8a2e1c09bd83",{lala:"popo",popo:"plpl"})
    let r4 = await test.delete("59a43779132f8a2e1c09bd83")

    //r3.toArray().then(r=>{res3=r});
    r2.toArray().then(r=>{response.json(r.concat(r4));});
  } catch (e) {
     console.log(e)
  }
});

```

Thanks in advance, any doubt: albertotorresfoltyn@hotmail.com
