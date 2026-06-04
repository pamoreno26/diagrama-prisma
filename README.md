# Mi Diagrama PRISMA

```mermaid
flowchart TD
    %% --- FILAS EN PARALELO (COLUMNA IZQUIERDA Y DERECHA) ---
    ID["<b>IDENTIFICATION</b><br><br>Records identified through database searching<br>(n = 475)"]
    
    SCR["<b>SCREENING</b><br><br>Records screened<br>(n = 475)"]
    EXC["Records excluded<br>(n = 412)"]
    
    ELG["<b>ELIGIBILITY</b><br><br>Full-text studies assessed for eligibility<br>(n = 63)"]
    DUP["Duplicate records removed<br>(n = 5)"]
    
    QA["<b>QUALITY ASSESSMENT</b><br><br>Studies assessed for quality<br>(n = 58)"]
    QAX["Studies excluded<br>(quality score ≤ 1.6)<br>(n = 10)"]
    
    INC["<b>INCLUDED</b><br><br>Studies included in the final synthesis<br>(n = 48)"]

    %% --- CONEXIONES VERTICALES RECTAS ---
    ID --> SCR
    SCR --> ELG
    ELG --> QA
    QA --> INC

    %% --- CONEXIONES HORIZONTALES RECTAS ---
    SCR --> EXC
    ELG --> DUP
    QA --> QAX

    %% --- ENLACES DE UNIÓN PARA CORREGIR LAS CURVAS ---
    %% Esto obliga a las cajas de la derecha a mantener la misma altura exacta que las de la izquierda
    SCR --- EXC
    ELG --- DUP
    QA --- QAX

    %% --- ESTILOS DE LAS CAJAS ---
    classDef cajaPrincipal fill:#FFFFFF,stroke:#000000,stroke-width:2px,color:#000000,font-family:Arial,sans-serif,font-size:13px;
    classDef cajaExclusion fill:#FFFFFF,stroke:#555555,stroke-width:1.5px,stroke-dasharray: 5 5,color:#000000,font-family:Arial,sans-serif,font-size:13px;

    class ID,SCR,ELG,QA,INC cajaPrincipal;
    class EXC,DUP,QAX cajaExclusion;
