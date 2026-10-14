# Conflicto de fusión

## 1. ¿Qué archivo entró en conflicto y por qué?

El archivo `README.md`. Los dos integrantes cambiamos la misma línea, el subtítulo de la sección del diagrama, en ramas distintas: Santiago en `conflicto-santiago-2` y Sofía en `conflicto-sofia`. Cuando la rama de Santiago ya se había integrado a `main`, la solicitud de incorporación de Sofía intentó cambiar esa misma línea. Git no pudo decidir cuál de los dos textos conservar y marcó el conflicto.

## 2. ¿Qué mostraba Git exactamente?

```
<<<<<<< conflicto-sofia
## Diagrama de clases de CoopeTica
=======
## Diagrama de clases del dominio
>>>>>>> main
```

Lo de arriba es lo que venía de la rama de Sofía. Lo de abajo es lo que ya estaba en `main`, que venía de la rama de Santiago.

## 3. ¿Cómo decidimos cuál versión conservar?

Revisamos los dos subtítulos y decidimos conservar **"Diagrama de clases del dominio"**, el de Santiago, porque describe mejor lo que muestra la imagen: el modelo del dominio completo de la cooperativa. Al resolverlo en GitHub borramos las tres líneas de marcadores (`<<<<<<<`, `=======` y `>>>>>>>`) y registramos el commit de resolución, pero por error quedaron las dos líneas de subtítulo. Lo notamos al revisar el README en `main` y lo corregimos en un commit posterior, dejando solo el subtítulo final.

## 4. ¿Qué haríamos distinto para evitarlo la próxima vez?

Acordar antes quién edita cada sección del README, y hacer `pull` de `main` antes de empezar a trabajar en una rama nueva. Así cada uno trabaja sobre la versión más reciente y no se pisan los cambios en la misma línea.
