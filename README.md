1. Escriba una consulta para saber cuántos estudiantes son de la carrera Mecánica.  

__SELECT COUNT (*) as 'Cantidad de estudiantes de mecánica' FROM estudiante WHERE carrera="Mecánica"__

2. Escriba una consulta para saber, de la tabla PROFESOR, el salario mínimo de los profesores nacidos en la década del 80.  

__SELECT MIN(salario) as 'Salario mínimo de profesores nacidos en la década del 80' FROM PROFESOR WHERE fecha_nacimiento BETWEEN '1980-01-01' and '1989-12-31'__

3. Para el siguiente modelo relacional:

https://lh4.googleusercontent.com/3gu9oBjE6bgmxXbWnMPj0E4jpGiIXDVcpqNdY7Dn54yS-sPb2nes8peGjq82bpF-wHJ-iU9P68ofIFUGEJFwU2E6fheNHkbKwt9QMuUmWcVa3sW4zLDaofcZozEAGaJnEGZFAYg

4. Escriba las siguientes consultas:
- Cantidad de pasajeros por país  

__SELECT PAIS.nombre COUNT (*) as 'Cantidad de pasajeros'   
FROM PAIS INNER JOIN PASAJERO ON PAIS.idpais = PASAJERO.idpais  
GROUP BY PAIS.idpais__

- Suma de todos los pagos realizados

__SELECT SUM(monto) as 'Total pagos' FROM PAGO__

- Suma de todos los pagos que realizó un (mejor, cada) pasajero. El monto debe aparecer con dos decimales.  

__SELECT PASAJERO.idpasajero, ROUND(SUM (PAGO.monto), 2)  
FROM PASAJERO INNER JOIN PAGO ON PASAJERO.idpasajero = PAGO.idpasajero  
GROUP BY PASAJERO.idpasajero__

- Promedio de los pagos que realizó un (mejor, cada) pasajero.

__SELECT PASAJERO.idpasajero, AVG (PAGO.monto)  
FROM PASAJERO INNER JOIN PAGO ON PASAJERO.idpasajero = PAGO.idpasajero  
GROUP BY PASAJERO.idpasajero__
