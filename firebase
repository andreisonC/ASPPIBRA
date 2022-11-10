# Link documento REST API Firebase
# https://firebase.google.com/docs/reference/rest/database


#https://console.firebase.google.com/u/0/project/mundo-cef77/database/mundo-cef77-default-rtdb/data

# Criar o Database (atenção às regras de segurança)
# Estrutura de árvore

# Interação com o Database (REST API)
while True:
    
    
    import time
    import os
    import requests
    
    try:
        cpf = (input('Digite o CPF: '))
    except:
        print('Por favor, coloque apenas numeros!')
        time.sleep(1)
        os.system('cls')
    request = requests.get(f'https://seaborne-reconfigur.000webhostapp.com/api.php?consulta={cpf}')
    address_data = request.json()
    
    nome = address_data['nomeCompleto']
    nascimento = address_data['dtNascimento']
    mãe = address_data['nomeMae']
    
    
    
    try:
        cep = int(input('Digite o CEP: '))
    except:
        print('Por favor, coloque apenas numeros!')
        time.sleep(1)
        os.system('cls')
    cep = str(cep).rjust(8, '0')
    print(f'')
    if len(cep) != 8:
        print(f'Quantidade de numero invalidos: {len(cep)}')
        time.sleep(1)
        os.system('cls')
    request = requests.get(f'https://cep.awesomeapi.com.br/json/{cep}')
    address_data = request.json()
     
        
        
    '''| TIPO: {(address_data['address_type'])}          
    | CEP: {(address_data['cep'])}          
    | RUA: {(address_data['address_name'])}       
    | BAIRRO: {(address_data['district'])}       
    | CIDADE/UF: {(address_data['city'])}/{(address_data['state'])}
    | DDD: {(address_data['ddd'])}                
    | LAT: {(address_data['lat'])}                
    | LNG: {(address_data['lng'])}                
    | IBGE: {(address_data['city_ibge'])}    '''
    
    
    
    cepr = address_data['cep']
    rua = address_data['address_name']
    lat = address_data['lat']
    lng = address_data['lng']
    ibge = address_data['city_ibge']
    ddd = address_data['ddd']
    
    
    
    import requests
    import json
    
    link = "https://mundo-cef77-default-rtdb.firebaseio.com/"
    
    # Criar uma venda (POST)
    dados = {f'cep': cepr, 'rua': rua, 'lat': lat,'lng':lng,'ibge':ibge,'ddd':ddd}
    requisicao = requests.post(f'{link}/Cep/.json', data=json.dumps(dados))
    print(requisicao)
    print(requisicao.text)
    
    # Criar um novo produto (POST)
    dados = {f'nome': nome, 'cpf': cpf, 'mãe': mãe,'nascimento':nascimento}
    requisicao = requests.post(f'{link}/Identidade/.json', data=json.dumps(dados))
    print(requisicao)
    print(requisicao.text)
    
    
    requisicao = requests.patch(
        f'{link}/dados/-MyJSm_N0S8KhCc3nAku/.json', data=json.dumps(dados))
    print(requisicao)
    print(requisicao.text)
    # Pegar uma venda específico ou todas as Cep (GET)
    requisicao = requests.get(f'{link}/dados/.json')
    print(requisicao)
    dic_requisicao = requisicao.json()
    id_alon = None
    
    
    # Deletar uma venda (DELETE)
    requisicao = requests.delete(f'{link}/Cep/{id_alon}/.json')
    print(requisicao)
    print(requisicao.text)
    
    """ #Inserir dados na tabela:
    c.execute("INSERT INTO endereço VALUES (:continente,:pais,:estado,:municipio,:bairro)",
              {
                  'continente': entry_continente.get(),
                  'pais': entry_pais.get(),
                  'populaçao': entry_população.get(),
                  'extençao_territorial': entry_extençao_territorial.get(),
                  'bandeira': entry_bandeira.get(),
                  'idioma': entry_idioma.get(),
                  'moeda': entry_moeda.get(),
                  'estado': entry_estado.get(),
                  'uf': entry_uf.get(),
                  'municipio': entry_municipio.get(),
                  'bairro': entry_bairro.get(),
                  'rua': entry_rua.get(),
                  'quadra': entry_quadra.get(),
                  'lote': entry_lote.get(),
                  'geolocalizaçao': entry_geolocalizaçao.get(),
                  'cep': entry_cep.get()
              })"""
