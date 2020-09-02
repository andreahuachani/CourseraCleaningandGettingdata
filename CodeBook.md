---

---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

**Libro de códigos del proyecto del curso "Obtención y limpieza de datos"**

Datos iniciales para la investigación
Los datos se toman de UCI HAR Dataset . Este conjunto de datos proporciona las siguientes variables para cada actividad:

1. asunto - ID del participante

2. actividad : ID del tipo de actividad

3. Desviación media y estándar para las siguientes características (otros valores se presentan en el conjunto de datos inicial, pero para esta investigación solo se usaron estos parámetros)
    * tBodyAcc-XYZ
    * tGravityAcc-XYZ
    * tBodyAccJerk-XYZ
    * tBodyGyro-XYZ
    * tBodyGyroJerk-XYZ
    * tBodyAccMag
    * tGravityAccMag
    * tBodyAccJerkMag
    * tBodyGyroMag
    * tBodyGyroJerkMag
    * fBodyAcc-XYZ
    * fBodyAccJerk-XYZ
    * fBodyGyro-XYZ
    * fBodyAccMag
    * fBodyAccJerkMag
    * fBodyGyroMag
    * fBodyGyroJerkMag
Las características provienen del acelerómetro y el giroscopio 3-axiales señales sin procesar tAcc-XYZ y tGyro-XYZ. Estas señales en el dominio del tiempo (prefijo 't' para indicar el tiempo) se capturaron a una tasa constante de 50 Hz. Luego se filtraron usando un filtro mediano y un filtro Butterworth de paso bajo de tercer orden con una frecuencia de esquina de 20 Hz para eliminar el ruido. De manera similar, la señal de aceleración se separó luego en señales de aceleración de cuerpo y gravedad (tBodyAcc-XYZ y tGravityAcc-XYZ) utilizando otro filtro Butterworth de paso bajo con una frecuencia de esquina de 0.3 Hz.

Posteriormente, la aceleración lineal del cuerpo y la velocidad angular se derivaron a tiempo para obtener señales de Jerk (tBodyAccJerk-XYZ y tBodyGyroJerk-XYZ). También se calculó la magnitud de estas señales tridimensionales utilizando la norma euclidiana (tBodyAccMag, tGravityAccMag, tBodyAccJerkMag, tBodyGyroMag, tBodyGyroJerkMag).

Finalmente se aplicó una Transformada Rápida de Fourier (FFT) a algunas de estas señales produciendo fBodyAcc-XYZ, fBodyAccJerk-XYZ, fBodyGyro-XYZ, fBodyAccJerkMag, fBodyGyroMag, fBodyGyroJerkMag. (Tenga en cuenta la 'f' para indicar señales de dominio de frecuencia).

Estas señales se utilizaron para estimar las variables del vector de características para cada patrón:
'-XYZ' se utiliza para indicar señales triaxiales en las direcciones X, Y y Z.