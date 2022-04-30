# spiderverse

## Diseño de Software con TDD

El TDD o Test-Driven Development (desarrollo dirigido por tests) es una práctica de programación que consiste en escribir primero las pruebas (generalmente unitarias), después escribir el código fuente que pase la prueba satisfactoriamente y, por último, refactorizar el código escrito.

![image](https://user-images.githubusercontent.com/74028526/166083432-4f161b5b-784b-443a-bba8-cd3e1bc3cb3f.png)



Implementar la clase spiderman que tenga como atributos: nombre, edad, actor que lo interpretó, número de películas en las que apareció, estudio de cine. Y utilizar el método que nos regrese la siguiente información: nombre y estudio al que pertenece el spiderman instanciado.

[![](https://mermaid.ink/img/pako:eNptkDEOwyAMRa-CPLVqTsDcDp2zsljYpEgBIjCVqih3L2nTTniy33-D7RVsIgYNdsZSrh6njMFE1epD1Lh44hwwfuF_VFpdIgbuYJy61ErKHR7S03PpBEUq-dQJJpZ7dOl0hgHCTj21A9bdNCAPbkuBbi2xwzqLARO3ptaFUPhGvu0B2uFceACsksZXtKAlV_5Jxx8Oa3sD2glhDg)](https://mermaid-js.github.io/mermaid-live-editor/edit#pako:eNptkDEOwyAMRa-CPLVqTsDcDp2zsljYpEgBIjCVqih3L2nTTniy33-D7RVsIgYNdsZSrh6njMFE1epD1Lh44hwwfuF_VFpdIgbuYJy61ErKHR7S03PpBEUq-dQJJpZ7dOl0hgHCTj21A9bdNCAPbkuBbi2xwzqLARO3ptaFUPhGvu0B2uFceACsksZXtKAlV_5Jxx8Oa3sD2glhDg)

~~~
class Spiderman{
    constructor (name, age, actor, movies, studio){
        this.name = name
        this.age = age
        this.actor = actor
        this.movies = movies
        this.studio = studio
    }
    getInfo(){
        return `Hey, I'm ${this.actor} from ${this.studio} studio`
    }
}

module.exports = Spiderman
~~~

Escribir las puebas unitarias
~~~
const Spiderman = require('./../app/spiderman')

describe("Unit Test for Spiderman class", () => {
    test('1) Create an spiderman object', () => {
        // Aquí escribimos el código que queremos usar tal cuál 
        // Quiero poder instanciar un objeto Spiderman con esta información
        const andrewGarfield = new Spiderman("Spiderman Sony", 31, "Andrew Garfield", 2, "Sony")

        // Validamos que este código funcione de la forma esperada
        expect(andrewGarfield.name).toBe("Spiderman Sony")
        expect(andrewGarfield.age).toBe(31)
        expect(andrewGarfield.actor).toBe("Andrew Garfield")
        expect(andrewGarfield.movies).toBe(2)
        expect(andrewGarfield.studio).toBe("Sony")
    });
    test('2) Use the method getInfo()', () => {
        const tomHolland = new Spiderman("Spidermna Marvel", 25, "Tom Holland", 5, "Marvel")
        expect(tomHolland.getInfo()).toBe("Hey, I'm Tom Holland from Marvel studio")
    });
  })
  ~~~
  
  Un refactor se aplica solo cuando se tiene una prueba de respaldo, que indicará que mejoras al código no rompen el comportamiento necesario.
  
