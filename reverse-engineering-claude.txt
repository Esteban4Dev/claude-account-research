# Análisis del Sistema de Baneos de Claude / Claude's Account Banning Mechanism Analysis



---



## [ESPAÑOL]

Este documento explica los hallazgos de la comunidad china sobre cómo funciona el mecanismo interno de baneos y suspensiones de cuentas de Claude de Anthropic, el cual opera bajo un sistema de puntuación invisible.



### ¿Cómo funciona el sistema?

Claude asigna una puntuación inicial a cada cuenta tras su registro. A partir de ahí, la cuenta gana o pierde puntos según las acciones del usuario. Si la puntuación cae por debajo de cierto límite, la cuenta es baneada automáticamente. Recuperar puntos es extremadamente difícil.



---



### Factores clave que afectan la puntuación:



#### 1. Registro (Registration)

* **IP limpia:** Es el factor más crítico. No requiere necesariamente ser residencial, pero el historial de la IP debe estar limpio.

* **Correo electrónico:** Gmail ya ha dejado de ser la opción óptima; existen otros servicios de correo con mayor peso/reputación ante sus filtros.

* **KYC inicial:** Si el sistema pide verificación de identidad (KYC) justo al registrarse, esa cuenta suele considerarse perdida.

* **Dispositivo:** Registrarse directamente desde la aplicación móvil otorga puntos positivos.



#### 2. Pagos y Suscripciones (Payment)

* **Suscripción inmediata:** Suscribirse justo después de crear la cuenta resta puntos.

* **Saltar a planes altos:** Pasar directamente al plan Max deduce una gran cantidad de puntos. Se recomienda esperar dos días y contratar primero el plan Pro.

* **KYC al pagar:** Si se solicita verificación durante el pago, significa que la cuenta entró en un periodo de revisión (aunque no necesariamente termine en baneo).

* **Método de pago:** Las tarjetas bancarias de entidades extranjeras suman puntos (al igual que Google Play), mientras que las tarjetas virtuales restan puntos.



#### 3. Uso y Comportamiento (Usage)

* **Límites de uso:** No se debe agotar el límite de mensajes de golpe. Es mejor alternar entre dos cuentas que llevar una sola al límite máximo.

* **Clientes oficiales:** Usar la aplicación de escritorio otorga un pequeño bono de puntos; se aconseja minimizar el uso de la versión web. La app móvil también suma puntos.

* **Función de Memoria:** Activar la función de memoria añade puntos. Entre más archivos de memoria posea la cuenta, mayor será su puntuación.



#### 4. IP y Dispositivos (IP and Device)

* **Estabilidad:** La estabilidad es clave. No se deben cambiar las IPs constantemente; conviene mantener la misma dirección el mayor tiempo posible.

* **Proxies:** Deben configurarse en modo global con la opción TUN activada.

* **Dispositivos múltiples:** Iniciar sesión desde varios dispositivos reduce drásticamente los puntos. Lo ideal es mantener la regla de "un ordenador, un cliente".

* **Concurrencia:** Cambios frecuentes de IP, inicios de sesión constantes y alta concurrencia penalizan fuertemente la puntuación.



#### 5. Antigüedad de la Cuenta (Account Age)

* Las cuentas antiguas poseen un margen de error muy amplio (las creadas en 2023 tienen una puntuación base netamente superior).

* La puntuación aumenta de forma natural con el tiempo, aunque este proceso es muy lento.



#### 6. Factores Misceláneos (Other)

* **Sistema operativo:** Windows y macOS no muestran diferencias, pero Linux resta puntos.

* **Zona horaria e idioma:** Prácticamente no tienen impacto. Usar la zona horaria de Pekín o decirle a Claude que eres de China no provoca un baneo automático por sí solo.

* **Uso de Fable:** Un uso intensivo de Fable resta puntos.

* **Riesgo del plan Max:** Salvo que se trate de una cuenta antigua con alta reputación, actualizar al plan Max suele colocar al usuario en un periodo de observación.



---



### Periodo de Observación y Baneos (Observation Period and Banning)

* **Señales de alerta:** Al acercarse al límite inferior de puntos, la cuenta puede entrar en un periodo de observación, cuyo síntoma más común es el cierre repentino de sesión.

* **Desenlace:** Si la cuenta sigue acumulando penalizaciones durante esta fase, se produce el baneo definitivo. 

* **Resiliencia:** Las cuentas con un puntaje inicial muy alto son capaces de sobrevivir a múltiples periodos de observación antes de ser suspendidas.



---

---



## [ENGLISH]

This document explains the findings of the Chinese community regarding how Anthropic Claude's internal account banning and suspension mechanism works, which operates under an invisible points system.



### How does the system work?

Claude assigns an initial score to each account upon registration. From there, the account gains or loses points based on user behavior. If the score falls below a certain threshold, the account is directly banned. Recovering points is extremely difficult.



---



### Key factors affecting scores:



#### 1. Registration

* **Clean IP:** The most important factor. It doesn't have to be residential broadband, but it must be clean.

* **Email:** Gmail is no longer the optimal choice; there are email services with higher weight.

* **Initial KYC:** Accounts that prompt for KYC right upon registration can be discarded.

* **Device:** Registering via the mobile app adds points.



#### 2. Payment

* **Immediate Subscription:** Subscribing immediately after registration deducts points.

* **Jumping to High Plans:** Jumping straight to Max deducts a large amount of points. It's best to wait two days and subscribe to Pro first.

* **KYC during Payment:** Being prompted for KYC during payment indicates the account is in a review period, but it won't necessarily get banned.

* **Payment Method:** Foreign entity bank cards add points. Google Play works too. Virtual cards deduct points.



#### 3. Usage

* **Usage Limits:** Don't exhaust the limit in one go. It's better to rotate between two accounts than to max out one.

* **Official Clients:** The desktop client gives a small points boost. Use the web version as little as possible. The mobile app also gives a small points boost.

* **Memory Feature:** Enabling the memory feature adds points. The more memory files, the higher the score.



#### 4. IP and Device

* **Stability:** Stability is key. Don't switch IPs; stick to the same one as much as possible.

* **Proxies:** Must be in global mode with TUN enabled.

* **Multiple Devices:** Logging in from multiple devices deducts a large amount of points. The ideal setup is one computer, one client.

* **Concurrency:** Frequent IP changes, frequent logins, and high concurrency all deduct a large amount of points.



#### 5. Account Age

* Old accounts have huge leeway for errors. 2023 accounts clearly score higher.

* Scores grow over time, but very slowly.



#### 6. Other

* **Operating System:** No difference between Windows and macOS. Linux deducts points.

* **Time Zone and Language:** Basically no impact. You won't get banned just for using Beijing time or telling Claude you're Chinese.

* **Fable Usage:** Heavy use of Fable deducts points.

* **Max Plan Risk:** Upgrading to Max likely puts you in an observation period, unless it's a high-weight old account.



---



### Observation Period and Banning

* **Warning Signs:** When nearing the threshold, the account may enter an observation period. A typical sign is getting logged out.

* **Outcome:** Continuing to deduct points during the observation period leads to a ban.

* **Resilience:** High-score accounts can survive multiple observation periods before being suspended.