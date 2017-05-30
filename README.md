# -scriptbackuppostgres
 #definir o formato da data

DATA=`date +%Y-%m-%d_%H-%M`
 
export pgpassword = " senha_do_postgres"

#

#pg_dump --  salva um banco de dados do PostgreSQL em um arquivo de script ou de outro tipo

pg_dump -U USUÁRIO_POSTGRES -h LOCAL_BANCO_DE_DADOS -O -o -b -F c NOME_BANCO_DADOS > NOME_DO_BACKUP.backup

#restaurar um banco de dados do PostgreSQL, a partir de um arquivo criado pelo pg_dump

pg_restore -U USUÁRIO_POSTGRES -h LOCAL_BANCO_DE_DADOS -d NOME_BANCO_DADOS NOME_DO_BACKUP.backup

#

#compactar o bakup

tar cvzf /backup/compact/$Data_backupPostgreSql.tgz /backup/postgresql$Data.backup
#
#apagar arquivo não compactado

rm -rf /backup/$data.dbserver.sql
