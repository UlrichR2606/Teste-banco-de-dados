[Uploading maimport sqlite3


banco = sqlite3.connect('facebook.db')
cursor = banco.cursor()

cursor.execute("create table Pessoa (id number, nome text, identidade number, cpf number, endereco text)")  

def f1():
    print('__________Digite seus dados__________\n')
    idi=input('ID: ')
    nom=input('NOME: ')
    RG=input('RG: ')
    CPF=input('CPF: ')
    cep=input('ENDEREÇO: ')
    cursor.execute(f"Insert INTO Pessoa VALUES ({idi}, '{nom}', {RG}, {CPF}, '{cep}')")
def f2():
    cursor.execute('''select * from Pessoa''')
    print(cursor.fetchall())

    deleta=input('Digite o seu id: ')
    cursor.execute(f'delete from Pessoa where id = {deleta} ')
    
  
def f3():
    print('~ ~ ~ ~ ~ ~ ~ ~UPDATE~ ~ ~ ~ ~ ~ ~ ~\n')
    esc=int(input('Digite seu ID: '))
    cursor.execute(f'''select * from Pessoa where id = {esc}''')
    print('\n')
    print(cursor.fetchall())
    
    
    mudar=int(input('''Difite o que deseja mudar
    (1) ID
    (2) NOME
    (3) RG
    (4) CPF
    (5) ENDEREÇO\n '''))
    if mudar == 1:
        ch=input('Digite o novo ID: ')
        cursor.execute(f'''UPDATE Pessoa set id = {ch} where id = {esc}''')
        cursor.execute(f'''select * from Pessoa where id = {ch}''')
        print (cursor.fetchall())
    elif mudar == 2:
        ch1=input('Digite o novo NOME: ')
        cursor.execute(f'''UPDATE Pessoa set nome = '{ch1}' where id = {esc}''')
        cursor.execute(f'''select * from Pessoa where id ={esc}''')
        print (cursor.fetchall())
    elif mudar == 3:
        ch2=input('Digite o novo RG: ')
        cursor.execute(f'''UPDATE Pessoa set identidade = {ch2} where id = {esc}''')
        cursor.execute(f'''select * from Pessoa where id ={esc}''')
        print (cursor.fetchall())
    elif mudar == 4:
        ch3=input('Digite o novo CPF: ')
        cursor.execute(f'''UPDATE Pessoa set cpf = {ch3} where id = {esc}''')
        cursor.execute(f'''select * from Pessoa where id ={esc}''')
        print (cursor.fetchall())
    elif mudar == 5:
        ch4=input('Digite o novo ENDEREÇO: ')
        cursor.execute(f'''UPDATE Pessoa set endereco = '{ch4}' where id = {esc}''')
        cursor.execute(f'''select * from Pessoa where id ={esc}''')
        print (cursor.fetchall())
    
    
   
def f4():
    sele=int(input('''________________Escolha________________
    (1) Id
    (2) Nome
    (3) RG
    (4) CPF
    (5) Endereço
    
    '''))
    if sele == 1:
         cursor.execute('''select a.id from Pessoa a''')
         print (cursor.fetchall())
    elif sele == 2:
         cursor.execute('''select a.nome from Pessoa a''')
         print(cursor.fetchall())
    elif sele == 3:
         cursor.execute('''select a.identidade from Pessoa a''')
         print(cursor.fetchall())
    elif sele == 4:
         cursor.execute('''select a.cpf from Pessoa a''')
         print(cursor.fetchall())
    elif sele == 5:
         cursor.execute('''select a.endereco from Pessoa a''')
         print(cursor.fetchall())
    else: print('é pra escolher um daqueles seu animal!')
def sair():
   print("Obrigado e adeus")

if __name__ == "__main__":
   switch = {
       "1": f1,
       "2": f2,
       "3": f3,
       "4": f4
   }
   b=input('''************************MENU SHOW DE BOLA************************
(1) inserir
(2) Apagar
(3) Mudar
(4) Selecionar

Digite um nunero: ''')

   case = switch.get(b, sair)
   case()
cursor.execute('''select * from Pessoa''')
print(cursor.fetchall())


banco.commit()



in.py…]()
