# iteso-bdnr-final-project-template

Plantilla (template) para el proyecto final de la materia de **Bases de Datos No Relacionales (BDNR)** en ITESO.

## Estructura del Repositorio

```text
iteso-bdnr-final-project-template/
├── data/
│   ├── data1.csv
│   ├── data2.csv
│   ├── dataX.csv
│   └── seeders/                        # Se extraen datos de un csv o se generan datos sintéticos.
│       ├── generator.py             
│       ├── cassandra_seeder.py
│       ├── mongo_seeder.py
│       ├── dgraph_seeder.py
│       ├── chroma_seeder.py          
│       └── seed.py                   
│
├── client/
│   └── menu.py                         # UN SOLO CLIENTE (cli, página, app de escritorio, etc.)
│
├── server/
│   ├── app.py                          # Punto de entrada
│   └── db/
│       ├── cassandra_db.py             # Conexión a Cassandra
│       ├── mongo_db.py                 # Conexión a MongoDB
│       ├── dgraph_db.py                # Conexión a Dgraph
│       ├── chroma_db.py                # EXTRA: Conexión a ChromaDB
│       │
│       └── services/                   # Un servicio por cada base de datos.
│           ├── cassandra_service/
│           │   ├── model.py            # Consultas en CQL
│           │   └── resources.py        # Endpoints del servicio de Cassandra
│           ├── mongo_service/
│           │   ├── model.py            # Consultas en MQL
│           │   └── resources.py        # Endpoints del servicio de MongoDB
│           ├── dgraph_service/
│           │   ├── model.py            # Consultas en DQL
│           │   └── resources.py        # Endpoints del servicio de Dgraph
│           ├── chroma_service/         # EXTRA
│           │   ├── model.py         
│           │   └── resources.py      
│           └── extra_service/          # EXTRA: Servicio que utilice bases de datos combinadas.
│               ├── model.py          
│               └── resources.py
│
├── README.md                           # Descripción del proyecto.
└── requirements.txt                    # cassandra-driver, pymongo, pydgraph, ...
```

## Requisitos y Configuración

1. **Crear entorno virtual**:
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```

2. **Instalar dependencias**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Cargar datos (seeders)**:
   ```bash
   python data/seeders/seed.py
   ```

4. **Iniciar servidor**:
   ```bash
   python server/app.py
   ```

5. **Iniciar cliente**:
   ```bash
   python client/menu.py
   ```
