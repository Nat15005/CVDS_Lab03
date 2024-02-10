# CVDS_Lab03
### CLASES DE EQUIVALENCIA
### CREAR UN PROYECTO CON MAVEN
En el directorio de trabajo ejecutar el comando necesario para crear/generar un proyecto maven basado en un arquetipo:
``` 
Grupo (groupId): edu.eci.cvds
Artefacto (artifactId): ClasesEquivalencia
Paquete (package): edu.eci.cvds.tdd
archetypeArtifactId: maven-archetype-quickstart
```
  ![image](https://github.com/Nat15005/CVDS_Lab03/assets/111907712/e750778b-7d23-459c-9554-15fd07b16ab9)

  ![image](https://github.com/Nat15005/CVDS_Lab03/assets/111907712/de28332b-68d9-42e3-974f-9a833e3510f1)

### ACTUALIZAR Y CREAR DEPENDENCIAS EN EL PROYECTO
Busque en internet el repositorio central de maven.
Busque el artefacto JUnit y entre a la versión más nueva

  ![image](https://github.com/Nat15005/CVDS_Lab03/assets/111907712/5c49d07e-880c-484e-93a7-2bb8046a3835)

Ingrese a la pestaña de Maven y haga click en el texto de la dependencia para copiarlo al portapapeles.

- Edite el archivo pom.xml y realice las siguientes actualizaciones:

- Agregue/Reemplace la dependencia copiada a la sección de dependencias.

![image](https://github.com/Nat15005/CVDS_Lab03/assets/111907712/c3f77774-535a-4859-a5f2-26578ed7e696)

- Hay que cambiar la versión delcompilador de Java a la versión 8, para ello, agregue la sección properties antes de la sección de dependencias:

![image](https://github.com/Nat15005/CVDS_Lab03/assets/111907712/d7856489-7be0-4460-8d42-636012608122)

### COMPILAR Y EJECUTAR
Ejecute los comandos necesarios de Maven, para compilar el proyecto y verificar que el proyecto se creó correctamente y los cambios realizados al archivo pom no generan inconvenientes.

![image](https://github.com/Nat15005/CVDS_Lab03/assets/111907712/11789bf1-5398-4fd6-abda-72a9afb180e0)

![image](https://github.com/Nat15005/CVDS_Lab03/assets/111907712/1a20b7fe-4342-4a38-a9d8-a35ee6de64c9)


Busque el comando requerido para ejecutar las pruebas unitarias de un proyecto desde Maven y ejecútelo sobre el proyecto. Se debe ejecutar la clase AppTest con resultado exitoso.

![image](https://github.com/Nat15005/CVDS_Lab03/assets/111907712/65253f5e-767e-4bd4-b8fc-e0d6159ee72e)

![image](https://github.com/Nat15005/CVDS_Lab03/assets/111907712/15732327-ba7d-4b00-ba13-945f08e5d359)

### EJERCICIO “REGISTRADURÍA”
Se va a crear un proyecto base para un cliente en la registraduría, en el cual se registrarán personas con intención de votar para las próximas elecciones y se generarán los certificados electorales de aquellas personas cuyo voto sea válido.
Se usará la clase persona qué se describe más adelante. El servicio de la registradiría permitirá registrar personas que sean votantes.

#### REQUERIMIENTOS
- Solo se registrarán votantes válidos
- Solo se permite una inscripción por número de documento

#### HACER EL ESQUELETO DE LA APLICACION
Cree el archivo RegisterResult.java en el directorio edu.eci.cvds.tdd.registry con la enumeración:

``` java
package edu.eci.cvds.tdd.registry;

public enum RegisterResult {
    DEAD, UNDERAGE, INVALID_AGE, VALID, DUPLICATED
}
```

![image](https://github.com/Nat15005/CVDS_Lab03/assets/111907712/6635a2a2-584e-4920-bb49-e9dc60bc5cbc)


Cree el archivo Gender.java en el paquete edu.eci.cvds.tdd.registry con la enumeración:

``` java
package edu.eci.cvds.tdd.registry;

public enum Gender {
    MALE, FEMALE, UNIDENTIFIED;
}
``` 

![image](https://github.com/Nat15005/CVDS_Lab03/assets/111907712/5b694f9f-b3a9-4545-933b-594afc070da1)


Cree el archivo Person.java en el paquete edu.eci.cvds.tdd.registry con el siguiente contenido:

``` java
package edu.eci.cvds.tdd.registry;
/**
 * Person representation Class
 */
public class Person {
    /**
     * Person's name
     */
    private String name;
    /**
     * A person's identification number
     */
    private int id;
    /**
     * Person's age
     */
    private int age;
    /**
     * Person's gender
     */
    private Gender gender;
    /**

     * Flag to specify if a person is alive
     */
    private boolean alive;
    /**
     * The class' default constructor
     */
    public Person() {
        super();
    }
    /**
     * A person constructor with all the information
     *
     * @param name the name
     * @param id the identification number
     * @param age the age
     * @param gender the gender
     * @param alive if the person is alive
     */
    public Person(String name, int id, int age, Gender gender, boolean alive) {
        this.name = name;
        this.id = id;
        this.age = age;
        this.gender = gender;
        this.alive = alive;
    }
    /**
     * Returns the person's name
     *
     * @return the name
     */
    public String getName() {
        return name;
    }
    /**
     * Returns the person's identification number *
     * @return the identification Number */
    public int getId() {
        return id;
    }
    /**
     * Returns this person's age
     *
     * @return the age
     */
    public int getAge() {
        return age;
    }
    /**
     * Returns the gender
     *
     * @return the gender
     */
    public Gender getGender() {
        return gender;
    }

    /**
     * Returns if the person is alive *
     * @return the alive
     */
    public boolean isAlive() {
        return alive;
    }
    /**
     * Sets the person's name
     *
     * @param name the name to set
     */
    public void setName(String name) {
        this.name = name;
    }
    /**
     * Sets the person's identification number *
     * @param id the identification Number to set */
    public void setId(int id) {
        this.id = id;
    }
    /**
     * Sets the person's age
     *
     * @param age the age to set
     */
    public void setAge(int age) {
        this.age = age;
    }
    /**
     * Sets the person's gender
     *
     * @param gender the gender to set
     */
    public void setGender(Gender gender) {
        this.gender = gender;
    }
    /**
     * Sets the flag to specify if this person is alive
     *
     * @param alive the alive to set
     */
    public void setAlive(boolean alive) {
        this.alive = alive;
    }
    /**
     * @{inheritdoc}
     */
    @Override
    public String toString() {
        return "Person [name=" + name + ", id=" + id + ", age=" + age + ", gender=" + gender + ", alive=" + alive + "]"; }
}

```

![image](https://github.com/Nat15005/CVDS_Lab03/assets/111907712/c63e09ae-0411-4c48-8255-50b3f0209e0f)

Cree el archivo Registry.java en el directorio edu.eci.cvds.tdd.registry con el método registerVoter:

 
``` java
package edu.eci.cvds.tdd.registry;
public class Registry {
    public RegisterResult registerVoter(Person p) {
        // TODO Validate person and return real result.
        return RegisterResult.VALID;
    }
}
```

![image](https://github.com/Nat15005/CVDS_Lab03/assets/111907712/27ccab15-6e51-4ea6-87d9-d2845fa82c43)

Cree la misma estructura de paquetes edu.eci.cvds.tdd.registry en la ruta src/test/java. Todos los archivos relacionados específicamente con los temas de pruebas, siempre deben ir bajo la carpeta test.

Bajo la carpeta de pruebas, cree la clase RegistryTest.java en el directorio edu.eci.cvds.tdd.registry de la siguiente manera:

``` java
package edu.eci.cvds.tdd.registry;

import org.junit.Assert;
import org.junit.Test;

public class RegistryTest {
    private Registry registry = new Registry();
    @Test
    public void validateRegistryResult() {
        Person person = new Person();
        RegisterResult result = registry.registerVoter(person);
        Assert.assertEquals(RegisterResult.VALID, result);
    }
    // TODO Complete with more test cases
}

```

![image](https://github.com/Nat15005/CVDS_Lab03/assets/111907712/b69cd671-70aa-4afe-abb4-b099afac94d4)

#### EJECUTAR LAS PRUEBAS
Para correr las pruebas utilice:

```
$ mvn package
```

También puede utilizar:

```
$ mvn test
```

Revise cual es la diferencia. 

![image](https://github.com/Nat15005/CVDS_Lab03/assets/111907712/6e6f4d03-7fb8-49b9-959d-5f1893436ee9)

#### FINALIZAR EL EJERCICIO

Piense en los casos de equivalencia que se pueden generar del ejercicio para la registraduría dadas las condiciones. Deben ser al menos 5.

- Valid
- Underage
- Invalid age
- Dead
- Duplicated
  
Complete la implementación de la clase RegistryTest.java con (al menos) un método por cada clase de equivalencia, creando diferentes personas y validando que el resultado sea el esperado.

![image](https://github.com/Nat15005/CVDS_Lab03/assets/111907712/781b0433-b5d6-4311-a0a8-7df383250feb)

![image](https://github.com/Nat15005/CVDS_Lab03/assets/111907712/b113a544-87df-4c36-8e0a-5d0c461d78d3)


Complete la implementación del método registerVoter en la clase Registry.java para retornar el resultado esperado según la entrada.


