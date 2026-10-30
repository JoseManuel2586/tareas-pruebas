# Entrega — Semana 15: Pruebas de Código

**Curso:** Programación IV  
**Proyecto:** tareas-pruebas  
**Estado:** Pruebas aprobadas y GitHub Actions en verde.

## 1. Resultados de las pruebas

Se corrigieron los seis errores identificados en el proyecto y se ejecutaron las pruebas correspondientes.

| Verificación | Resultado |
|---|---|
| Pruebas unitarias y de integración | 35 aprobadas |
| Pruebas E2E con Playwright | 5 aprobadas |
| Pruebas de mutación | 6 de 6 mutantes detectados |
| Cobertura de líneas | 95.12 % |
| GitHub Actions | Aprobado |

## 2. Explicación de los seis errores corregidos

**Error 1 — `diasEntre` (`lib/precios.ts`):** La función sumaba un día adicional al calcular la diferencia entre fechas; lo detectaron las pruebas unitarias que verificaban el conteo de días y los cambios de mes.

**Error 2 — `aplicarCupon` (`lib/precios.ts`):** La función permitía que un descuento superior al subtotal generara un importe negativo; lo detectó la prueba unitaria que verifica que el cobro nunca sea negativo.

**Error 3 — `calcularTotal` (`lib/precios.ts`):** La función calculaba el IVA antes de aplicar el descuento; lo detectaron las pruebas unitarias que verificaban el desglose completo y la base del IVA.

**Error 4 — `suscripcionesActivas` (`lib/repo.ts`):** La consulta incluía suscripciones canceladas y morosas porque no filtraba por estado; lo detectó la prueba de integración que comprueba que solo se devuelvan las suscripciones activas del equipo.

**Error 5 — `canjearCupon` (`lib/repo.ts`):** La función permitía superar el límite de canjes cuando había solicitudes simultáneas; lo detectó la prueba de integración que ejecuta diez solicitudes concurrentes.

**Error 6 — Checkout (`app/checkout/page.tsx`):** La pantalla mostraba un total que no descontaba el cupón; lo detectó la prueba E2E que comprueba que el total mostrado coincida con el importe cobrado.

## 3. Comprobante de verificación

Comando ejecutado:

`pnpm verificar`

Resultado:

```text
T+ L+ U+ I+ C+ M+ E+   2f99423a3123   2026-10-30 19:19 UTC
```

## 4. GitHub Actions

La ejecución del flujo de integración continua finalizó correctamente.

**Ejecución aprobada:**

https://github.com/JoseManuel2586/tareas-pruebas/actions/runs/41120791253

## 5. Evidencias

Se cuenta con capturas de pantalla de las siguientes ejecuciones:

- `pnpm pruebas`: 35 pruebas aprobadas.
- `pnpm mutantes`: 6 de 6 mutantes detectados.
- GitHub Actions: ejecución aprobada.

Las capturas se adjuntarán en la descripción del Pull Request.