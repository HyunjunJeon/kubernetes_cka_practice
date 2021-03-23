!pip install cx_Oracle 

!sudo apt install libaio

import cx_Oracle
import os

LOCATION = r"/home/jovyan/instantclient_21_1/"
os.environ["PATH"] = LOCATION + ":" + os.environ["PATH"] #환경변수 등록
os.putenv('NLS_LANG', '.UTF8')

print(os.environ["PATH"])

user_id='system'
pass_word='oracle'
oracle_ip='10.111.143.148'
oracle_port='1521'
oracle_sid='xe'

conn = cx_Oracle.connect(user_id,
                         pass_word,
                         f"{oracle_ip}:{oracle_port}/{oracle_sid}")

cursor = conn.cursor()