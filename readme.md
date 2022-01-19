Validación esquemas AVRO
========================

Para comprobar que los esquemas están bien formados se deben dejar los esquemas (con extensión `.avsc`) en el directorio `./src/main/resources/avro` y compilar el proyecto `mvn clean package`. No debe existir ningún error de compilación. Verificar las clases generadas en el `target`.

Dentro de los esquemas avro, se debe comprobar que se siguen las siguientes convenciones en las propiedades de primer nivel:

- `namespace`: `com.santalucia.<topic_domain>.<topic_subdomain>.<topic_functionality>.avro` en formato _snake_case_
- `name`: `<topic_functionality><type>` en formato _UpperCamelCase_.

Por ejemplo:

- key schema:
  ```json
  {
    "type" : "record",
    "name" : "PersistidosKey",
    "namespace" : "com.santalucia.cartera.polizas_odl.persistidos.avro",
    "fields" : [ {...} ]
  }
  ```
- value schema:
  ```json
  {
    "type" : "record",
    "name" : "PersistidosValue",
    "namespace" : "com.santalucia.cartera.polizas_odl.persistidos.avro",
    "fields" : [ {...} ]
  }
  ```
  
