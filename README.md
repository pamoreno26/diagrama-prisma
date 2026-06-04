# Mi Diagrama PRISMA

```mermaid
architecture-beta
    group flujo(tb) [Flujo Principal]
    group excluidos(tb) [Exclusiones]

    node ID(rect) [IDENTIFICATION<br>n=475] in flujo
    node SCR(rect) [SCREENING<br>n=475] in flujo
    node ELG(rect) [ELIGIBILITY<br>n=63] in flujo
    node QA(rect) [QUALITY ASSESSMENT<br>n=58] in flujo
    node INC(rect) [INCLUDED<br>n=48] in flujo

    node EXC(rect) [Records excluded<br>n=412] in excluidos
    node DUP(rect) [Duplicate records<br>n=5] in excluidos
    node QAX(rect) [Studies excluded<br>n=10] in excluidos

    ID:B -> SCR:T
    SCR:B -> ELG:T
    ELG:B -> QA:T
    QA:B -> INC:T

    SCR:R -> EXC:L
    ELG:R -> DUP:L
    QA:R -> QAX:L
