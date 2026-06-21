# Eszközök és kapcsolattesztek

Ez a dokumentum a laborban használt adatbázis-kezelő eszközöket és az első kapcsolódási / SQL futtatási teszteket foglalja össze.

A cél ebben a részben nem a telepítési folyamat dokumentálása, hanem annak bemutatása, hogy az adatbázis-kezelő eszközök elindulnak, a kapcsolatok működnek, és minden környezetben végrehajtható egy egyszerű SQL lekérdezés.

## Használt adatbázis-kezelő eszközök

### MySQL Workbench

![MySQL Workbench kezdőképernyő](../images/01_tools_and_connection_tests/01_mysql_workbench_home.png)

### Toad for Oracle

![Toad for Oracle kezdőképernyő](../images/01_tools_and_connection_tests/02_oracle_toad_home.png)

### pgAdmin

![pgAdmin kezdőképernyő](../images/01_tools_and_connection_tests/03_postgresql_pgadmin_home.png)

### SQL Server Management Studio 22

![SQL Server Management Studio kezdőképernyő](../images/01_tools_and_connection_tests/04_sqlserver_ssms_home.png)

### DBeaver Community

![DBeaver kezdőképernyő](../images/01_tools_and_connection_tests/05_dbeaver_home.png)

## Kapcsolódási és alap SQL tesztek

Minden adatbázisban egy egyszerű dátum/idő lekérdezés futott le. Ezek a tesztek azt ellenőrzik, hogy az adott klienseszköz sikeresen csatlakozik az adatbázishoz, és képes SQL-t futtatni.

A kapcsolattesztek SQL fájljai itt találhatók:

```text
sql/01_connection_tests/
├── oracle.sql
├── sqlserver.sql
├── postgresql.sql
├── mysql.sql
├── db2.sql
└── sqlite.sql
```

### Oracle Database

```sql
SELECT SYSDATE
FROM dual;
```

![Oracle Toad SELECT teszt](../images/01_tools_and_connection_tests/06_oracle_toad_select_test.png)

### Microsoft SQL Server

```sql
SELECT GETDATE() AS current_datetime;
```

![SQL Server SSMS SELECT teszt](../images/01_tools_and_connection_tests/07_sqlserver_ssms_select_test.png)

### PostgreSQL

```sql
SELECT CURRENT_TIMESTAMP;
```

![PostgreSQL pgAdmin SELECT teszt](../images/01_tools_and_connection_tests/08_postgresql_pgadmin_select_test.png)

### MySQL

```sql
SELECT NOW() AS current_datetime;
```

![MySQL Workbench SELECT teszt](../images/01_tools_and_connection_tests/09_mysql_workbench_select_test.png)

### IBM Db2

```sql
SELECT CURRENT TIMESTAMP
FROM SYSIBM.SYSDUMMY1;
```

![IBM Db2 DBeaver SELECT teszt](../images/01_tools_and_connection_tests/10_db2_dbeaver_select_test.png)

### SQLite

```sql
SELECT datetime('now') AS current_datetime;
```

![SQLite DBeaver SELECT teszt](../images/01_tools_and_connection_tests/11_sqlite_dbeaver_select_test.png)

## Összegzés

Ebben a részben mind a hat adatbázis-környezet működőképesnek bizonyult:

- a klienseszközök elindultak;
- az adatbázis-kapcsolatok létrejöttek;
- mindenhol lefutott egy egyszerű SQL lekérdezés;
- az eredmények képernyőképeken is dokumentálva vannak.
