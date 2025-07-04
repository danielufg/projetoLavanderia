# projetoLavanderia
Projeto acadêmico relacionado a um programa simples de reservas direcionado à lavanderias.


Diagrama de Classes
https://www.plantuml.com/plantuml/png/nLZVRnit37xtNw6tdh6qs5wDegWNDwYtkYlivAt0G9zOHwXEz2HTqFte_xwSh6DqF1-oh0FsTlxuYQ8-KPJero62ZsrZP-6pSKVmqAY67DMtdXfKqRTOM6eB8InZz6RVHbpNv7Rc3rJV5nH76WCUrGybwC5zpc2aeugazXGZDKeRZtKqv6QpP-goyuvXbcPHAuYmXu0RS710h_wSAVLShPRNon-NkpU_tcpVBTGkUkCEoL2JSoTNEsfzZGjrAP14QqCBtj0AQA5MG2zlJhylrDf5FA1_bLXm18_sze6sp83WUGpexu1fszFl0UixPPo9rNoXxiZe11mmtd0SdMKgaaJDSsUk24UISmJCdOgfjXIGW_ew4w9djNN--HuQd51xeNxI-rfgtOVpW5VpAUPqDFqoSpH6BvHnCNqtfD7I82QDeVQcXY5Qmn5geq7ZpuU7uN10f-4ExKBjYIo2ExamuKZE29ptMTCGhjiGxo5DxTwcXVH4NysPcN1hzkZ1oonOwmunBYOW922lKZ0tQRtLdDUM1Z0-b4ECNVN2oE6bIQeddLmMEegW1oQfjrp8ibTUIXHAstX_v9fufyP-IYFlwAIdRR-t8qUbRPm1KfysnEIYo8RGmuD4AGT6EebTx0nd_wKrw69t55C6qS6uge7eJTrQID9Ug83k5lgXHVpiv2rvy8R2bVb2eJz7BdPhiHG-WFRTZhyp8RvSzt0UmpM53Q6QJt6BiC5yWJpJVrjj6tG13jYiS7bd0Wro6RIf3JdmEx2QgZpnMcUTkb1zlm5YdpNkJPmOoB5bu9p4IzqOPqBqeCd_szrAU_89QbJBDgABfkwo_zlsVkr215SRy1luhJKEGlPds31TSxTuf60Y-T_vBg37Bf_7RwZQ8qIi85iNFDtyuJCHswEU9FBfqMZn7v8-a3zVMos1llBKb5RsmuobjPpxsLZcl3mEMR9Ryh1sNMBU3wKQxBLfa2rNff7mrI_RpVBw-iss4p5YXr-HRo16zBt8RzbfYeZ7ipbv5hP7Iiq68sbQuGSuG8CkzWkm9aGu6KDU_Mdegs7EvZh96VkaUn131564HIBdiZ6TafamdP6I8nCo7_j5FzMSl_fid629D9EKfsJYlWqr-7lpfZ_eRtRT4N_auFDK4-ai23ARiwr8vhmNqsfdmhJQaYFLpjcnwAUQyrUlzWHBgYqfttJkHHHIg6mR2tNcTIgp8El7USudK5O9Xhb4331jO0Ccz9Vwm3QkWWaE4M8R1dVbfrHIG9DVGOIgY2lNZ7iOByvNhmIBqiK5XHyCA_ciNOaj46rG9P8qi6NoG77ASV3oTLiQfrR9tcHjbSu6jhFA25TSXuKVDaWTsOFi-ofv8ON2DjvruMMNzb-6mVWmFVgnilAUIN573LvISxGOXtdBrOgvmu9rGi1gVX0__OsJHZGKeWU_0aroVVfKky1Nuk5NbeVzDE79xTdxGWsfjR1smatqM5punRIC2tt4y9DF9e_ZE5qdGjFIHMRmG8R1whAvuVpOOGsQFEHhl_zPVNHAjEWN7IIQp8oEMiQ4Zbl010zQgOzkbB7vgRl2Tt07-JakmFybkcTgYnPIZv9UM64MwO3n5bECtEmzV_xNgw8K3deBOMIr4rwK2B5SOVuww-TwyQB3YtPZDfnkRE-T95Fnwflbp_kfEC01nhEdxZ13ij5W8_ieR6Dw8ef_2MTYu0GhX_O8Qzm_JGN-6frk6_it

Código do Diagrama de Classes
@startuml
skinparam monochrome true
skinparam classAttributeIconSize 0
skinparam nodesep 10
skinparam ranksep 10
top to bottom direction

' Classes
class DatabaseManager {
  - DATABASE_URL: String
  - connectionSource: ConnectionSource
  - usuarioDao: Dao<Usuario, Integer>
  - aparelhoDao: Dao<Aparelho, Integer>
  - reservaDao: Dao<Reserva, Integer>
  + init(): void
  + getUsuarioDao(): Dao<Usuario, Integer>
  + getAparelhoDao(): Dao<Aparelho, Integer>
  + getReservaDao(): Dao<Reserva, Integer>
  + close(): void
}

class Database {
  - databaseName: String
  - connection: JdbcConnectionSource
  + getConnection(): JdbcConnectionSource
  + close(): void
}

class Aparelho {
  - id: int
  - modelo: String
  - descricao: String
  - capacidadeKg: int
  - agendavel: boolean
  - disponivel: boolean
  - reservado: boolean
  - custo: double
  + reservar(): boolean
  + liberar(): void
  + getId(): int
  + setId(id: int): void
  + getModelo(): String
  + setModelo(modelo: String): void
  + getDescricao(): String
  + setDescricao(descricao: String): void
  + getCapacidadeKg(): int
  + setCapacidadeKg(capacidadeKg: int): void
  + getAgendavel(): boolean
  + setAgendavel(agendavel: boolean): void
  + getDisponivel(): boolean
  + setDisponivel(disponivel: boolean): void
  + getReservado(): boolean
  + setReservado(reservado: boolean): void
  + getCusto(): double
  + setCusto(custo: double): void
  + toString(): String
}

class Cliente {
  + login(matricula: int, senha: String): boolean
}

class HorariosFixos {
  - intervalosPadrao: List<IntervaloHorario>
  + getIntervalos(): List<IntervaloHorario>
}

class Caixa {
  - usuarioDao: Dao<Usuario, Integer>
  - aparelhoDao: Dao<Aparelho, Integer>
  - mensagemDeAviso: String
  + adicionarSaldo(usuarioId: int, valor: double): boolean
  + debitarSaldo(usuarioId: int, aparelhoId: int): boolean
}

class Administrador {
  + login(matricula: int, senha: String): boolean
}

interface Autenticavel {
  + login(matricula: int, senha: String): boolean
}

class InstanciarMaquinas {
  + instanciar(): void
}

class AparelhoRepository {
  - dao: Dao<Aparelho, Integer>
  + getDao(): Dao<Aparelho, Integer>
  + create(aparelho: Aparelho): Aparelho
  + update(aparelho: Aparelho): void
  + delete(aparelho: Aparelho): void
  + deletePorId(id: int): void
  + loadFromId(id: int): Aparelho
  + loadAll(): List<Aparelho>
}

class IntervaloHorario {
  - horaInicio: LocalTime
  - horaFim: LocalTime
  - FORMATTER: DateTimeFormatter
  + getHoraInicio(): LocalTime
  + getHoraFim(): LocalTime
  + toString(): String
}

class MetodoDePagamento {
  - listaMetodos: List<String>
}

interface Reservavel {
  + reservar(): boolean
  + liberar(): void
  + estaReservado(): boolean
}

class UsuarioRepository {
  - dao: Dao<Usuario, Integer>
  + getDao(): Dao<Usuario, Integer>
  + create(usuario: Usuario): Usuario
  + update(usuario: Usuario): void
  + delete(usuario: Usuario): void
  + deletePorId(id: int): void
  + buscarPorMatriculaESenha(matricula: int, senha: String): Usuario
  + loadFromId(id: int): Usuario
  + loadAll(): List<Usuario>
}

class ReservaRepository {
  - dao: Dao<Reserva, Integer>
  + getDao(): Dao<Reserva, Integer>
  + create(reserva: Reserva): Reserva
  + update(reserva: Reserva): void
  + delete(reserva: Reserva): void
  + deletePorId(id: int): void
  + loadFromId(id: int): Reserva
  + loadAll(): List<Reserva>
}

class Reserva {
  - id: int
  - usuario: Usuario
  - dataReserva: String
  - horaInicio: String
  - horaFim: String
  - diaMaisHorarios: String
  - aparelho: Aparelho
  - status: String
  + formatadorData(dataReserva: LocalDate, horaInicio: LocalTime, horaFim: LocalTime): String
  + getID(): int
  + setID(id: int): void
  + getUsuario(): Usuario
  + setUsuario(usuario: Usuario): void
  + getDataReserva(): String
  + setDataReserva(dataReserva: LocalDate): void
  + getHoraInicio(): String
  + setHoraInicio(horaInicio: LocalTime): void
  + getHoraFim(): String
  + setHoraFim(horaFim: LocalTime): void
  + getAparelho(): Aparelho
  + setAparelho(aparelho: Aparelho): void
  + getStatus(): String
  + setStatus(status: String): void
}

class Usuario {
  - id: int
  - nomeCompleto: String
  - matricula: int
  - senha: String
  - saldo: double
  + login(matricula: int, senha: String): boolean
  + mostrarDados(): String
  + depositar(valor: double): void
  + debitar(valor: double): void
  + getId(): int
  + setId(id: int): void
  + getNomeCompleto(): String
  + setNomeCompleto(nome: String): void
  + getMatricula(): int
  + setMatricula(matricula: int): void
  + getStringMatricula(): String
  + setSenha(senha: String): void
  + getSenha(): String
  + getSaldo(): double
}

class Secadora {
  + Secadora(\n  modelo: String,\n  descricao: String,\n  capacidadeKg: int,\n  agendavel: boolean,\n  custo: double\n): void
}

class MaquinaDeLavar {
  + MaquinaDeLavar(\n  modelo: String,\n  descricao: String,\n  capacidadeKg: int,\n  agendavel: boolean,\n  custo: double\n): void
}

' Relacionamentos
together {
  Cliente --|> Usuario
  Administrador --|> Usuario
  Secadora --|> Aparelho
  MaquinaDeLavar --|> Aparelho
}
Cliente ..|> Autenticavel
Administrador ..|> Autenticavel
Aparelho ..|> Reservavel
Reserva --> Usuario
Reserva --> Aparelho
Caixa --> AparelhoRepository
Caixa --> UsuarioRepository
AparelhoRepository --> DatabaseManager
UsuarioRepository --> DatabaseManager
ReservaRepository --> DatabaseManager
InstanciarMaquinas --> AparelhoRepository
@enduml
