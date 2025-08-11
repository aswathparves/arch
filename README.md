# arch
```mermaid
graph TD
  %% Presentation Layer
  subgraph Presentation Layer
    FE[Frontend]
    APK[APK API]
  end

  %% Application Layer
  subgraph Application Layer
    BE[Backend]
    BEA[Backend - Alternate]
    REP[Report Service]
    WAL[Wallet Service]
    PAY[Payment Gateway]
  end

  %% Data Layer
  subgraph Data Layer
    RDSI[RDS - Internal]
    RDSP[RDS - Public]
    MWI[MongoDB - Wallet Internal]
    MWP[MongoDB - Wallet Public]
    MSI[MongoDB - System Internal]
    MSP[MongoDB - System Public]
    RED[Redis]
    PRED[Promo Redis]
  end

  %% Flow
  FE --> BE
  FE --> BEA
  APK --> BE
  APK --> BEA
  BE --> REP
  BE --> WAL
  BE --> PAY
  BEA --> WAL
  WAL --> PAY
  BE --> RDSI
  BE --> RDSP
  WAL --> MWI
  WAL --> MWP
  BE --> MSI
  BE --> MSP
  BE --> RED
  WAL --> PRED
```
