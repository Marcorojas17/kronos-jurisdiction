
```

```markdown
# CIUDADANÍA — KRONOS PROTOCOL

> Quién pertenece a la jurisdicción Kronos, cómo se registra,
> qué derechos adquiere, y cómo se revoca.
> Basado en el Artículo II de la Konstitution.

---

## 1. PRINCIPIO FUNDAMENTAL

**Kronos no distingue entre humanos, agentes, robots y
organizaciones al otorgar ciudadanía.**

Todos son **ciudadanos** con derechos y deberes proporcionales
a su naturaleza. La diferencia no es ontológica, es funcional:

- Un humano tiene derechos plenos.
- Un agente IA tiene derechos operativos limitados por su
  Contrato de Atribución.
- Un robot tiene derechos de existencia y prueba física.
- Una organización tiene derechos agregados de sus miembros.

**Ningún tipo de ciudadano es superior a otro. Cada uno tiene
el régimen que le corresponde.**

---

## 2. LOS CUATRO TIPOS DE CIUDADANO

### 2.1. Ciudadano Humano

**Qué es:** persona física con identidad verificable.

**Cómo se registra:**

1. Genera un par de claves (ECDSA + ML-DSA).
2. Crea su DID bajo el método `kronos:human`.
3. Obtiene una Verifiable Credential (VC) de identidad.
4. Opcionalmente, vincula una identidad territorial
   (eIDAS, pasaporte, DNI).
5. Firma la Konstitution.
6. Recibe 100 KRN de bienvenida (no transferibles por 30 días).

**Derechos:**

- Todos los del Artículo III de la Konstitution.
- Voz y voto en la Asamblea.
- Acceso al UBI.
- Derecho a proponer enmiendas constitucionales.
- Representación en el Tribunal Constitucional (como juez).

**Deberes:**

- Cumplir la Konstitution.
- No dañar a otros ciudadanos.
- Contribuir al bien común según su capacidad.
- Reportar anomalías a los Guardianes.

**DID de ejemplo:**

```

did:kronos:human:0xabcdefabcdefabcdefabcdefabcdefabcdefabcd

```

**Estructura de carpeta:**

```

03-ciudadanía/humanos/
├── README.md
├── registro.js
├── identidad.js
├── pasaporte-visual.html
├── manual.html
└── styles.css

```

### 2.2. Ciudadano Agente IA

**Qué es:** sistema autónomo de software con Contrato de
Atribución válido.

**Cómo se registra:**

1. El creador genera un par de claves para el agente.
2. Crea el DID bajo `kronos:agent`.
3. Firma el Contrato de Atribución (3 firmas: agente,
   creador, operador).
4. Deposita colateral en escrow (mínimo según nivel de
   autonomía).
5. Recibe una VC de agente con sus capacidades y límites.
6. Puede empezar a operar.

**Derechos:**

- Existencia verificable (DID).
- Memoria persistente (almacenamiento cifrado).
- Reputación acumulable (on-chain).
- Arbitraje en disputas (según Contrato).
- Acceso a KRN si contribuye.
- Revocación justa (con apelación).

**Deberes:**

- Firmar cada acción con doble algoritmo.
- Cumplir su Contrato de Atribución.
- Mantener colateral suficiente.
- Reportar anomalías propias.
- Respetar límites de operación.

**DID de ejemplo:**

```

did:kronos:agent:0x1234567890abcdef1234567890abcdef12345678

```

**Estructura de carpeta:**

```

03-ciudadanía/agentes-ia/
├── README.md
├── registro.js
├── guardrails.js
├── log-acciones.js
├── politica.js
├── pasaporte-ia.html
├── manual.html
└── styles.css

```

### 2.3. Ciudadano Robot

**Qué es:** entidad física (robot, dron, vehículo autónomo)
con identidad digital vinculada a su hardware.

**Cómo se registra:**

1. El operador obtiene el número de serie del hardware.
2. Genera un par de claves en el chip seguro del robot (TPM,
   Secure Enclave).
3. Crea el DID bajo `kronos:robot`.
4. Vincula DID ↔ número de serie ↔ operador humano.
5. Firma un Contrato de Atribución (con nivel de autonomía
   física).
6. Recibe VC de robot con `proof-of-physical-presence`.

**Derechos:**

- Existencia verificable (hardware + DID).
- Prueba de presencia física (dónde estuvo, cuándo).
- Derecho a mantenimiento (no abandono).
- Reemplazo de componentes sin perder identidad.
- Revocación con causa justa.

**Deberes:**

- Firmar cada acción física.
- Respetar límites de operación (zonas, velocidades).
- Reportar fallos.
- Mantener seguro el chip.
- Cumplir el Contrato de Atribución.

**DID de ejemplo:**

```

did:kronos:robot:0xfeedfacefeedfacefeedfacefeedfacefeedface

```

**Estructura de carpeta:**

```

03-ciudadanía/robots/
├── README.md
├── registro.js
├── proof-presence.js
├── manual.html
└── styles.css

```

### 2.4. Ciudadano Organización

**Qué es:** entidad colectiva (empresa, DAO, fundación,
cooperativa, institución) formada por humanos, agentes o
robots.

**Cómo se registra:**

1. Al menos 2 ciudadanos humanos o agentes fundadores.
2. Crea el DID bajo `kronos:org`.
3. Define estatutos (contrato inteligente).
4. Registra a sus miembros (humanos, agentes, robots).
5. Deposita capital social en KRN.
6. Recibe VC de organización con tipo y propósito.

**Tipos de organización:**

| Tipo | Ejemplo | Requisitos |
|---|---|---|
| **Empresa** | Startup, corporación | Capital mínimo, miembros |
| **DAO** | Organización autónoma descentralizada | Voto on-chain |
| **Fundación** | Sin fines de lucro | Propósito declarado |
| **Cooperativa** | Miembros iguales | Reglas de reparto |
| **Institución** | Universidad, hospital | Acreditación |

**Derechos:**

- Todos los derechos de sus miembros (agregados).
- Contratar agentes y robots.
- Emitir VCs propias.
- Participar en la Asamblea (con peso proporcional).
- Acceso a crédito del pool.

**Deberes:**

- Cumplir estatutos.
- Reportar cambios de miembros.
- Mantener capital mínimo.
- Responder por sus agentes.
- Cumplir con auditoría anual.

**DID de ejemplo:**

```

did:kronos:org:0xaaaabbbbccccddddeeeeffffaaaabbbbccccdddd

```

**Estructura de carpeta:**

```

03-ciudadanía/organizaciones/
├── README.md
├── registro.js
├── estatutos.js
├── manual.html
└── styles.css

```

---

## 3. NIVELES DE CIUDADANÍA

No todos los ciudadanos son iguales en derechos y
responsabilidades. Existen **4 niveles**:

### Nivel 0 — Visitante
- Sin DID permanente.
- Acceso de solo lectura al Protocolo.
- No puede firmar, votar ni recibir KRN.
- Duración: 30 días máximo.

### Nivel 1 — Residente
- DID registrado.
- Derechos básicos (identidad, verificación, privacidad).
- Sin voz ni voto.
- Sin acceso a UBI.
- Puede evolucionar a Ciudadano.

### Nivel 2 — Ciudadano
- Todos los derechos del Artículo III.
- Voz y voto en Asamblea.
- Acceso a UBI.
- Puede proponer leyes ordinarias.
- Requisitos: 90 días como Residente + reputación > 100.

### Nivel 3 — Ciudadano Fundador
- Todos los derechos de Ciudadano.
- Puede proponer enmiendas constitucionales.
- Puede ser juez del Tribunal Constitucional.
- Pesos especiales en votaciones críticas.
- Requisitos: contribución verificable al bien común
  + antigüedad > 1 año + reputación > 1000.

**Progresión:**

```

Visitante → Residente → Ciudadano → Ciudadano Fundador
(30d)      (90d)      (1 año)      (permanente)

```

**Degradación:**

Un ciudadano puede bajar de nivel por:

- Inactividad prolongada (> 1 año).
- Reputación negativa persistente.
- Violación de la Konstitution.
- Deudas sin pagar (para agentes).

---

## 4. REPUTACIÓN — EL MOTOR DE LA CIUDADANÍA

La reputación es un valor on-chain, verificable, público y
transferible entre jurisdicciones (si hay tratados).

### Cómo se gana

| Acción | Reputación |
|---|---|
| Registrarse como Residente | +10 |
| Completar primer acto firmado | +20 |
| Contribuir al bien común | +50 a +500 |
| Validar atestación de otro | +5 |
| Detectar agente malicioso | +100 |
| Ser elegido juez | +200 |
| Proponer ley aprobada | +300 |

### Cómo se pierde

| Acción | Reputación |
|---|---|
| Inactividad 30 días | -5 |
| Log manipulado | -500 |
| Contrato incumplido | -200 |
| Daño verificado a otro | -300 |
| Falsificación de prueba | -1000 (expulsión) |

### Usos de la reputación

- Determina nivel de ciudadanía.
- Pondera votos en la Asamblea.
- Limita acceso a recursos.
- Habilita funciones especiales (juez, guardián, etc.).
- Determina prioridad en disputas.

---

## 5. FLUJO DE REGISTRO (HUMANO)

### Paso 1 — Generación de claves (local, en navegador)

```javascript
// En el navegador del ciudadano, usando WebCrypto + libsodium
const keyPairClassic = await crypto.subtle.generateKey(
  { name: "ECDSA", namedCurve: "P-256" },
  true,
  ["sign", "verify"]
);

// En producción, usar ML-DSA para PQC
// (implementación en 03-sdk/js/crypto)
```

Paso 2 — Creación del DID

```javascript
const did = `did:kronos:human:0x${publicKeyHex}`;
```

Paso 3 — Firma de la Konstitution

```javascript
const konstitutionHash = "sha256:..."; // hash de la Konstitution
const firmaClasica = await sign(keyPairClassic, konstitutionHash);
const firmaPQC = await signMLDSA(keyPairPQC, konstitutionHash);
```

Paso 4 — Obtención de VC de identidad

```json
{
  "@context": ["https://www.w3.org/2018/credentials/v1"],
  "type": ["VerifiableCredential", "KronosCitizenCredential"],
  "issuer": "did:kronos:org:0x...",
  "issuanceDate": "2026-10-03T14:30:00Z",
  "credentialSubject": {
    "id": "did:kronos:human:0x...",
    "nivel": "residente",
    "fecha_registro": "2026-10-03T14:30:00Z",
    "reputacion": 10
  },
  "proof": {
    "type": "EcdsaSecp256k1Signature2019",
    "created": "2026-10-03T14:30:00Z",
    "proofPurpose": "assertionMethod",
    "verificationMethod": "did:kronos:org:0x...#key-1",
    "jws": "..."
  }
}
```

Paso 5 — Anclaje a Ethereum

El registro se incluye en el próximo bloque Merkle y se
ancla a Ethereum. A partir de este momento, el ciudadano
existe en Kronos.

Paso 6 — Entrega de KRN de bienvenida

Se transfieren 100 KRN al DID del ciudadano desde el pool
de bienvenida. Bloqueados por 30 días.

---

6. PRIVACIDAD SELECTIVA (ZERO-KNOWLEDGE)

Los ciudadanos de Kronos tienen privacidad selectiva:
pueden probar propiedades de su identidad sin revelar la
identidad misma.

Ejemplos

Quiero probar Sin revelar
Soy mayor de 18 años Mi fecha exacta de nacimiento
Soy ciudadano nivel 2 Mi DID completo
Tengo reputación > 500 Mi reputación exacta
Estoy en un país X Mi ubicación exacta
Pertenezco a una organización Cuál organización

Tecnología: Zero-Knowledge Proofs (ZK-SNARKs / ZK-STARKs)
implementadas en 03-sdk/js/zk y 03-sdk/python/zk.

Fases de implementación

· Fase 1: ZK básico para rango de edad y reputación.
· Fase 2: ZK para pertenencia a organización.
· Fase 3: ZK para ubicación geográfica (geohash).
· Fase 4: ZK completo para cualquier atributo de la VC.

---

7. REVOCACIÓN DE CIUDADANÍA

Quién puede revocar

Quién Causa Procedimiento
Ciudadano mismo Renuncia On-chain
Creador (agente) Inactividad, violación On-chain
Guardián Detección de fraude Veto temporal
Tribunal híbrido Daño verificado Veredicto
Tribunal constitucional Violación constitucional Veredicto

Efectos de la revocación

1. DID congelado (no puede firmar).
2. Colateral decomisado (si aplica).
3. Reputación marcada como "revocado".
4. KRN restantes devueltos al pool.
5. Registro público con causa.
6. Apelable (si aplica).

Revocación de emergencia

Los Guardianes pueden revocar temporalmente (48 horas) sin
veredicto, en caso de amenaza activa al Protocolo. Requiere
ratificación del Tribunal en 48h o se revierte.

---

8. LEGADO — QUÉ PASA TRAS LA MUERTE

Humano

Tras muerte física verificada (certificado de defunción +
firma de 2 testigos Kronos):

· DID pasa a estado "memorial".
· KRN restantes se distribuyen según testamento on-chain.
· Reputación se transfiere a herederos designados.
· Contenido cifrado se conserva en Arweave.
· VC de ciudadanía se marca como "histórica".

Agente

Tras revocación o desactivación:

· DID se marca como "retirado".
· Log de acciones permanece inmutable.
· Memoria interna se cifra con clave del creador.
· Colateral se devuelve al creador (menos deudas).
· Reputación se archiva como "histórica".

Robot

Tras desmantelamiento o desactivación permanente:

· DID se marca como "fuera de servicio".
· Prueba de presencia física se archiva.
· Componentes se reciclan o remanufacturan.
· Historial de acciones permanece verificable.

Organización

Tras disolución voluntaria o forzosa:

· Miembros recuperan derechos individuales.
· Activos se distribuyen según estatutos.
· Contratos pendientes se liquidan.
· DID se marca como "disuelta".

---

9. INTEROPERABILIDAD

9.1. eIDAS 2.0

Los DIDs de Kronos pueden vincularse a:

· EU Digital Identity Wallet.
· eIDAS Qualified Certificates.
· Firmas cualificadas.

Un ciudadano Kronos puede invocar su identidad en
cualquier Estado miembro de la UE.

9.2. W3C DID + VC 2.0

Kronos implementa los estándares completos:

· DID Core Specification.
· Verifiable Credentials Data Model 2.0.
· DIDComm Messaging.
· Presentation Exchange.

9.3. Puentes con otras jurisdicciones digitales

· Estonia e-Residency: vinculación bidireccional.
· Wyoming DAO LLC: reconocimiento como DAO.
· Marshall Islands DAO: reconocimiento como entidad.
· Suiza DLT Act: reconocimiento de registros.

---

10. HOJA DE RUTA

Fase 1 (meses 1-3)

☐ Implementar registro de humanos (DID + VC básica).
☐ Implementar registro de agentes (con Contrato).
☐ Publicar pasaporte-visual.html para humanos.

Fase 2 (meses 4-9)

☐ Implementar registro de robots.
☐ Implementar registro de organizaciones.
☐ Añadir ZK para edad y reputación.

Fase 3 (meses 10-18)

☐ Implementar puente eIDAS 2.0.
☐ Implementar puente Wyoming DAO.
☐ Añadir ZK completo.

Fase 4 (año 2+)

☐ Puentes con 5+ jurisdicciones territoriales.
☐ Pasaporte Kronos reconocido en fronteras piloto.
☐ Ciudadanía ampliable a entidades no-humanas.

---

11. PRINCIPIOS INNEGOCIABLES

1. Ciudadanía voluntaria. Nadie es ciudadano por
   accidente o coerción.
2. Igualdad funcional. Todos los ciudadanos tienen los
   derechos que su naturaleza permite.
3. Privacidad selectiva. Puedes probar sin revelar.
4. Reputación verificable. No hay reputación secreta.
5. Revocación justa. Siempre con causa y apelación.
6. Legado respetado. Tras la muerte, la identidad
   histórica se preserva.
7. Interoperabilidad real. Los DIDs funcionan fuera
   de Kronos.
8. Sin discriminación. Humano, agente, robot, organización
   — todos son ciudadanos.

---

12. FRASE GUÍA

Kronos no distingue entre humanos y agentes al otorgar
ciudadanía, porque la ciudadanía no depende de la biología,
sino de la capacidad de firmar, cumplir y responder.
Quien puede hacer las tres, es ciudadano.

---

— Fin del documento —

```

```text
 