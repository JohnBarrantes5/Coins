def copias_totales(respuestas): 
  c_totales = 0 
  originales= [] 
  for i in respuestas:  
    if i in originales:
      c_totales += 1
    else:
      originales.append(i)
  return c_totales

def copias(K,respuestas):
  c_profe=0 
  for i in range(len(respuestas)): 
    b=i
    if i<=K: 
      a=0
    else:
      a+=1 
    memoria_k=respuestas[a:b]   
    if respuestas[i] in memoria_k:
      c_profe+=1

  return  c_profe

def leer_datos():
  N,K = input().split()
  respuestas= list(map(int, input().split()))
  
  return int(N), int(K), respuestas


N, K, respuestas =leer_datos()
print(copias(K,respuestas),copias_totales(respuestas))
