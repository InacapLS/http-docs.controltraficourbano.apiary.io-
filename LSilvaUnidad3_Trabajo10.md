# http-docs.controltraficourbano.apiary.io-
Control de trafico urbano 2015

Profesor Rodrigo Salinas
06-09-2015
FORMAT: 1A
HOST: http://polls.apiblueprint.org/

# Control Tráfico Urbano

Sistema de control de trafico urbano.

+ Headers

        Accept-Charset: utf-8
        Connection: keep-alive
        Content-Type: multipart/form-data, boundary=AaB03x
        
## Camara en tiempo real [/camtiemporeal]
+ Attributes
 + id (number, required) - Identity
 + NumeroImg (number, required)) - Obligatorio
 + TiempoMs (number)
 + ImgBytes (number)
 

### Camtiemporeal [GET]

+ Response 200 (application/json)

        [
            {
                 "TiempoReal": {
                    "Id": 1,
                    "NumeroImg": 123032,
                    "TiempoMs": 100,
                    "TransInd": 201,
                    "ImgBytes": 2334
                  }
            }
        ]
+ Response 404 (application/json)
    + Headers

            Location: /camtiemporeal/Id

    + Body
                
                
                {
                "result": True,
                "message": "No encontrado(a)"
                }
### Crea nueva cam [POST]

+ Request (application/json)

        {
          "TiempoReal": {
            "Id": ,
            "NumeroImg":22,
            "TiempoMs":14000,
            "TransInd":3240,
            "ImgBytes":4300
          }
        }

+ Response 201 (application/json)

    + Headers
            
            Location: /camtiemporeal/Id/NumeroImg/22/TiempoMs/14000/TransInd/3240/ImgBytes/4300
            
    + Body

            {
                  "TiempoReal": {
                    "Id": ,
                    "NumeroImg":22,
                    "TiempoMs":14000,
                    "TransInd":3240,
                    "ImgBytes":4300
                  }   
            }
+ Response 404 (application/json)
    + Headers

            Location: /camtiemporeal/Id

    + Body
                
                
                {
                "result": True,
                "message": "No encontrado(a)"
                }
                
+ Response 409 (application/json)
    + Headers

            Location: /camtiemporeal/Id
            
    + Body
                
                
                {
                "result": True,
                "message": "El recurso ya existe."
                }
### Actualiza Cam [PUT]
+ Request (application/json)
        

            {
              "TiempoReal": {
                "Id": ,
                "NumeroImg":25,
                "TiempoMs":14500,
                "TransInd":3250,
                "ImgBytes":4300
              }
        }

+ Response 204 (application/json)

    + Headers
            
            Location: /camtiemporeal/Id/NumeroImg/25/TiempoMs/14500/TransInd/3250/ImgBytes/4300
            

+ Response 400 (application/json)

    + Headers        
            
            Location: /camtiemporeal/Id
    
    + Body
    
              {
                 "result": True,
                 "message": "no encontrada"
              }

+ Response 404 (application/json)

    + Headers   
            
            Location: /camtiemporeal/Id
            
    + Body
    
              {
                 "result": True,
                 "message": "no disponible"
              }
### Elimina Cam [DELETE]
+ Response 404 (application/json)

    + Headers
            
            Location: /camtiemporeal/Id
     
     
     
    + Body
            
             {
                "result": True,
                "message": "Cámara no encontrada"
                }
                
+ Response 200 (application/json)
    + Headers
            
            Location: /camtiemporeal/Id
     
     
     
    + Body
            
             {
                "result": True,
                "message": "Cámara eliminada"
                }


##TransmisionCam [/transmitsioncam]

### TransmiteCam [GET]


+ Response 200 (application/json)

            {
             {
                "ID":,
                "IdCamara":1205,
                "Nombre":"Cam Foscam IP FI8905W",
                "Codigo":"CamFI8905W",
                "Tamano":120,
                "Largo":200,
                "Fecha":"03/09/2015",
                "TiempoReal": {
                    "Id": ,
                    "NumeroImg": 123032,
                    "TiempoMs": 100,
                    "TransInd": 201,
                    "ImgBytes": 2334,
                 "ubicacion": {
                        "Id":,
                        "Ubicacion": "Alameda Gral.Bernardo O´Higgins ",
                        "Lat": "-33.44317211114969",
                        "Lon": "-70.65781510449221"
                      }
                  }
            }

+ Response 404 (application/json)
    + Headers

            Location: /camtiemporeal/Id

    + Body
                
                
                {
                "result": True,
                "message": "No encontrado(a)"
                }



##ListCamaras [/listacamaras]


### ListaCamaras [GET]


+ Response 200 (application/json)

            {
             {
                "ID":1,
                "IdCamara":1205,
                "Nombre":"Cam Foscam IP FI8905W",
                "Codigo":"CamFI8905W",
                "Tamano":100,
                "Largo":200,
                "Fecha":"03/09/2015",
                    "Ubicacion": {
                    "Id":,
                    "Calle_1":"Alameda gral. Bernardo O´Higgins",
                    "Calle_2":"Teatinos",
                    "Comuna": "Santiago centro",
                    "Ciudad": "Santiago",
                    "Region": "Metropolitana"
                  }
              },
              {
                "ID":2,
                "IdCamara":1205,
                "Nombre":"Cam Foscam IP FI8905W",
                "Codigo":"CamFI8905W",
                "Tamano":120,
                "Largo":200,
                "Fecha":"04/09/2015",
                    "Ubicacion": {
                    "Id":,
                    "Calle_1":"Huerfanos",
                    "Calle_2":"Teatinos",
                    "Comuna": "Santiago centro",
                    "Ciudad": "Santiago",
                    "Region": "Metropolitana"
                  }
              },
             {
                "ID":3,
                "IdCamara":1205,
                "Nombre":"Cam Foscam IP FI8905W",
                "Codigo":"CamFI8905W",
                "Tamano":220,
                "Largo":200,
                "Fecha":"04/09/2015",
                     "Ubicacion": {
                    "Id":,
                    "Calle_1":"Amunategui",
                    "Calle_2":"Teatinos",
                    "Comuna": "Santiago centro",
                    "Ciudad": "Santiago",
                    "Region": "Metropolitana"
                  }
                
              }              
            }

+ Response 404 (application/json)
    + Headers

            Location: /camtiemporeal

    + Body
                
                
                {
                "result": True,
                "message": "No encontrado(a)"
                }








            
## Video [/Video]
+ Attributes
 + ID (number, required) - Identity
 + IdCamara (number, required) - Obligatorio
 + Nombre (string)
 + Codigo (string)
 + Tamano (number)
 + Largo (number) 
 + Fecha (object) 
  

### Video [GET]

+ Response 200 (application/json)

        [
             {
                "ID":1,
                "IdCamara":1205,
                "Nombre":"Cam Foscam IP FI8905W",
                "Codigo":"CamFI8905W",
                "Tamano":120,
                "Largo":200,
                "Fecha":"03/09/2015"
           }
        ]
+ Response 404 (application/json)
    + Headers

            Location: /video/Id/IdCamara/1205/Nombre/Cam Foscam IP FI8905W/Codigo/CamFI8905W/Tamano/120/Largo/200/Fecha/03/09/2015

    + Body
                
                
                {
                "result": True,
                "message": "No encontrado(a)"
                }
### Crear nuevo video [POST]

+ Request (application/json)

        {
             {
                "ID":1,
                "IdCamara":1206,
                "Nombre":"Cam Foscam IP XP8905R",
                "Codigo":"CamXP8905R",
                "Tamano":120,
                "Largo":200,
                "Fecha":"04/09/2015"
           }
        }

+ Response 201 (application/json)

    + Headers

            Location: /video/Id/IdCamara/1206/Nombre/Cam Foscam IP XP8905R/Codigo/CamXP8905R/Tamano/120/Largo/200/Fecha/04/09/2015

    + Body

            {
                "ID":1,
                "IdCamara":1206,
                "Nombre":"Cam Foscam IP XP8905R",
                "Codigo":"CamXP8905R",
                "Tamano":120,
                "Largo":200,
                "Fecha":"04/09/2015"
            }
+ Response 404 (application/json)
    + Headers

            Location: /video/Id

    + Body
                
                
                {
                "result": True,
                "message": "No encontrado(a)"
                }
                
+ Response 409 (application/json)
    + Headers

            Location: /video/Id
            
    + Body
                
                
                {
                "result": True,
                "message": "El recurso ya existe."
                }
### Actualiza video [PUT]
+ Request (application/json)

        {
                "ID":1,
                "IdCamara":1206,
                "Nombre":"Cam Foscam IP XP8905R",
                "Codigo":"CamXP8905R",
                "Tamano":120,
                "Largo":200,
                "Fecha":"04/09/2015"
          }
        }

+ Response 204 (application/json)

    + Headers
            
             Location: /video/Id/IdCamara/1206/Nombre/Cam Foscam IP XP8905R/Codigo/CamXP8905R/Tamano/120/Largo/200/Fecha/04/09/2015
    
+ Response 400 (application/json)

    + Headers        
            
            Location: /video/Id
    
    + Body
    
              {
                 "result": True,
                 "message": "no encontrada"
              }

+ Response 404 (application/json)

    + Headers   
            
            Location: /video/Id
            
    + Body
    
              {
                 "result": True,
                 "message": "no disponible"
              }         
### Eliminar video [DELETE]
+ Response 404 (application/json)

    + Headers
            
            Location: /video/Id

    + Body
            
             {
                "result": True,
                "message": "video no encontrado"
                }
                
                
                
+ Response 200 (application/json)
     
    + Headers
            
            Location: /camtiemporeal/Id
     
     
    + Body
            
             {
                "result": True,
                "message": "video eliminado"
                }           



## Usuario [/Usuario]
+ Attributes
 + ID(number, required) - Identity
 + IDUsuario (number, required) - Obligatorio
 + Nombre (string) 
 + ApellidoPaterno (string) 
 + ApellidoMaterno (string) 
 + Ubicacion (string) 


### Usuario [GET]

+ Response 200 (application/json)

        [
            {
                "ID":1,
                "IDUsuario":10,
                "Nombre":"Mario",
                "ApellidoPaterno":"Gonzalez",
                "ApellidoMaterno":"Perez",
                "Ubicacion":"Las parcelas 132"
            }
        ]
+ Response 404 (application/json)
    + Headers

            Location: /usuario/Id/IDUsuario/10/Nombre/Mario/ApellidoPaterno/Gonzalez/ApellidoMaterno/Perez/Ubicacion/Las parcelas 132

    + Body
                
                
                {
                "result": True,
                "message": "No encontrado(a)"
                }
### Crea usuario [POST]


+ Request (application/json)

        [
            {
                "ID":1,
                "IDUsuario":11,
                "Nombre ": "Rodrigo",
                "ApellidoPaterno ":"Salinas",
                "ApellidoMaterno ":"Martinez",
                "Ubicacion":"Santiago centro"
            }
        ]

+ Response 201 (application/json)

    + Headers

            Location: /usuario/Id/IDUsuario/11/Nombre/Rodrigo/ApellidoPaterno/Salinas/ApellidoMaterno/Martinez/Ubicacion/Santiago centro

    + Body

            {
                "ID":1,
                "IDUsuario":11,
                "Nombre ": "Rodrigo",
                "ApellidoPaterno ":"Salinas",
                "ApellidoMaterno ":"Martinez",
                "Ubicacion":"Santiago centro"
            }
+ Response 404 (application/json)

    + Headers

            Location: /usuario/Id

    + Body
                
                
                {
                "result": True,
                "message": "No encontrado(a)"
                }
                
+ Response 409 (application/json)
    + Headers

            Location: /usuario/Id
            
    + Body
                
                
                {
                "result": True,
                "message": "El recurso ya existe."
                }
### Actualiza usuario [PUT]
+ Request (application/json)

        {
                "ID":1,
                "IDUsuario":11,
                "Nombre ": "Rodrigo",
                "ApellidoPaterno ":"Salinas",
                "ApellidoMaterno ":"Martinez",
                "Ubicacion":"Santiago centro"
          }
        }

+ Response 204 (application/json)

    + Headers
            
             Location: /usuario/Id/IDUsuario/11/Nombre/Rodrigo/ApellidoPaterno/Salinas/ApellidoMaterno/Martinez/Ubicacion/Santiago centro
             
+ Response 400 (application/json)

    + Headers        
            
            Location: /usuario/Id
    
    + Body
    
              {
                 "result": True,
                 "message": "no encontrada"
              }

+ Response 404 (application/json)

    + Headers   
            
            Location: /usuario/Id
            
    + Body
    
              {
                 "result": True,
                 "message": "no disponible"
              }         
              
### Elimina usuario [DELETE]
+ Response 404 (application/json)

    + Headers
            
            Location: /usuario/Id
    
    + Body
            
             {
                "result": True,
                "message": "Usuario no encontrado"
                }
                
+ Response 200 (application/json)
     
    + Headers
            
            Location: /usuario/Id
     
     
    + Body
            
             {
                "result": True,
                "message": "Usuario eliminado"
                }                 
                        

## Disco [/Disco]
+ Attributes
 + Id (number, required) - Identity
 + Compresion (number)
 + Fichero (string)
 + Tasa (number)
 + Tiempo (number)


### Disco [GET]

+ Response 200 (application/json)

        [
          "Disco": {
            "Id":1,
            "Compresion":1202,
            "Fichero": Avi,
            "Tasa":2000,
            "Tiempo":3
          }
        ]
+ Response 404 (application/json)
    + Headers

            Location: /Disco/Id
    + Body
                
                
                {
                "result": True,
                "message": "No encontrado(a)"
                }
### Crea Disco [POST]


+ Request (application/json)

        [
            {
            "Id":1,
            "Compresion":1202,
            "Fichero": "Avi",
            "Tasa":2000,
            "Tiempo":3
                        }
        ]

+ Response 201 (application/json)

    + Headers

            Location: disco/Id/Compresion/1202/Fichero/Avi/Tasa/2000/Tiempo/3

    + Body

            {
                  "Disco": {
                    "Compresion": 220,
                    "Fichero": "Fichero.avi ",
                    "Tasa": 200,
                    "Tiempo": 4
                  }
            }
+ Response 404 (application/json)

    + Headers

            Location: /disco/Id

    + Body
                
                
                {
                "result": True,
                "message": "No encontrado(a)"
                }
                
+ Response 409 (application/json)

    + Headers

            Location: /disco/Id
            
    + Body
                
                
                {
                "result": True,
                "message": "El recurso ya existe."
                }
### Actualiza Disco [PUT]
+ Request (application/json)

        {
                  "Disco": {
                    "Compresion": 220,
                    "Fichero": "Fichero.avi ",
                    "Tasa": 200,
                    "Tiempo": 4
          }
        }

+ Response 204 (application/json)

    + Headers
            
            Location: /disco/id/Compresion/220/Fichero/Fichero.avi/Tasa/200/Tiempo/4
            

+ Response 400 (application/json)

    + Headers        
            
            Location: /disco/Id
    
    + Body
    
              {
                 "result": True,
                 "message": "no encontrada"
              }

+ Response 404 (application/json)

    + Headers   
    
            Location: /disco/Id
            
    + Body
    
              {
                 "result": True,
                 "message": "no disponible"
              }
### Elimina Disco [DELETE]
+ Response 404 (application/json)

    + Headers
            
            Location: /disco/Id
            
    + Body
            
             {
                "result": True,
                "message": "Disco no encontrado"
                }
                
+ Response 200 (application/json)
     
    + Headers
            
            Location: /disco/Id
     
     
    + Body
            
             {
                "result": True,
                "message": "Disco eliminado"
                }        



## Ubicacion [/ubicacion]
+ Attributes
 + Id (string, required) - Identity
 + Calle_1 (string)
 + Calle_2 (string)
 + Comuna (string)
 + Ciudad (string)
 + Region (string)


### Ubicacion [GET]

+ Response 200 (application/json)

        [
              "Ubicacion": {
                "Id":1,
                "Calle_1":"Alameda gral. Bernardo O´Higgins",
                "Calle_2":"Teatinos",
                "Comuna": "Santiago centro",
                "Ciudad": "Santiago",
                "Region": "Metropolitana"
              }
        ]
+ Response 404 (application/json)
    + Headers

            Location: /ubicacion/Id        
    + Body
                
                
                {
                "result": True,
                "message": "No encontrado(a)"
                }
### Crea ubicacion [POST]


+ Request (application/json)

        [
            {
              "Ubicacion": {
                "Id":2,
                "Calle_1":"Brasil",
                "Calle_2":"catedral",
                "Comuna": "Santiago centro",
                "Ciudad": "Santiago",
                "Region": "Metropolitana"
              }
        ]

+ Response 201 (application/json)

    + Headers

            Location: /ubicacion/Calle_1/Brasil/Calle_2/catedral/Comuna/Santiago centro/Ciudad/Santiago/Region/Metropolitana

    + Body

            {
              "Ubicacion": {
                "Id":2,
                "Calle_1":"Alameda gral. Bernardo O´Higgins",
                "Calle_2":"Teatinos",
                "Comuna": "Santiago centro",
                "Ciudad": "Santiago",
                "Region": "Metropolitana"
              }
                  
            }
+ Response 404 (application/json)
    + Headers

            Location: /ubicacion/Id

    + Body
                
                
                {
                "result": True,
                "message": "No encontrado(a)"
                }
                
+ Response 409 (application/json)
    + Headers

            Location: /ubicacion/Id
            
    + Body
                
                
                {
                "result": True,
                "message": "El recurso ya existe."
                }
### Actualiza ubicacion [PUT]
+ Request (application/json)

        {
              "Ubicacion": {
                "Id":3,
                "Calle_1":"Brasil",
                "Calle_2":"Alte. barroso",
                "Comuna": "Santiago centro",
                "Ciudad": "Santiago",
                "Region": "Metropolitana"
              }
        }

+ Response 204 (application/json)

    + Headers
            
            Location: /ubicacion/Calle_1/Brasil/Calle_2/Alte. barroso/Comuna/Santiago centro/Ciudad/Santiago/Region/Metropolitana
            

+ Response 400 (application/json)

    + Headers        
    
            Location: /ubicacion/Id
            
    + Body
    
              {
                 "result": True,
                 "message": "no encontrada"
              }

+ Response 404 (application/json)

    + Headers   
            
            Location: /ubicacion/Id
        
    + Body
    
              {
                 "result": True,
                 "message": "no disponible"
              }
### Elimina Ubicacion [DELETE]
+ Response 404 (application/json)

    + Headers
            
            Location: /ubicacion/Id            
    + Body
            
             {
                "result": True,
                "message": "Ubicacion no encontrada"
                }
                
+ Response 200 (application/json)
     
    + Headers
            
            Location: /ubicacion/Id
     
     
    + Body
            
             {
                "result": True,
                "message": "Ubicacion eliminada"
                }




## Prediccion [/prediccion]
+ Attributes
 + Id (string, required) - Identity
 + Temperatura (number)
 + Vientos (enum[boolean])
    +Si
    +No
 + Lluvia (enum[boolean])
    +Si
    +No
 + Nieve (enum[boolean])
    +Si
    +No 
 + Sol (enum[boolean])
    +Si
    +No 
 + Nubes (enum[boolean])
    +Si
    +No 
 + Humedad (enum[boolean])
    +Si
    +No 

### prediccion [GET]

+ Response 200 (application/json)

        [
              "Prediccion": {
                "Id":1,
                "Temperatura": 18,
                "Vientos": "True",
                "Lluvia": "True",
                "Nieve": "False",
                "Sol": "True ",
                "Nubes": "True ",
                "Humedad": "True"
              }
                    ]
+ Response 404 (application/json)
    + Headers

            Location: /prediccion/Id         
    + Body
                
                
                {
                "result": True,
                "message": "No encontrado(a)"
                }                    
### Crea prediccion [POST]


+ Request (application/json)

        [
            {
                  "Prediccion": {
                    "Id":2,
                    "Temperatura": 22,
                    "Vientos": "False",
                    "Lluvia": "False",
                    "Nieve": "False",
                    "Sol": "True",
                    "Nubes": "False" ,
                    "Humedad": "5"
                  }
            }
        ]

+ Response 201 (application/json)

    + Headers

            Location: /prediccion/Temperatura/18/Vientos/True/Lluvia/True/Nieve/False/Sol/True/Nubes/True/Humedad/True    

    + Body

            {
                  "Prediccion": {
                    "Id":2,
                    "Temperatura": 22,
                    "Vientos": "False",
                    "Lluvia": "False",
                    "Nieve": "False",
                    "Sol": "True",
                    "Nubes": "False" ,
                    "Humedad": "5"
                  }
            }
+ Response 404 (application/json)
    + Headers

            Location: /prediccion/Id  

    + Body
                
                
                {
                "result": True,
                "message": "No encontrado(a)"
                }
                
+ Response 409 (application/json)
    + Headers

            Location: /camtiemporeal/Id
            
    + Body
                
                
                {
                "result": True,
                "message": "El recurso ya existe."
                }
### Actualiza prediccion [PUT]
+ Request (application/json)

        {
                  "Prediccion": {
                    "Id":1,
                    "Temperatura": 20,
                    "Vientos": "False",
                    "Lluvia": "False",
                    "Nieve": "False",
                    "Sol": "True",
                    "Nubes": "True ,
                    "Humedad": "15"
                  }
                  }
        }

+ Response 204 (application/json)

    + Headers
            
            Location: /prediccion/Temperatura/18/Vientos/True/Lluvia/True/Nieve/False/Sol/True/Nubes/True/Humedad/True    
            

+ Response 400 (application/json)

    + Headers        
    
    
    + Body
    
              {
                 "result": True,
                 "message": "no encontrada"
              }

+ Response 404 (application/json)

    + Headers   
    
    + Body
    
              {
                 "result": True,
                 "message": "no disponible"
              }                
### Elimina prediccion [DELETE]
+ Response 404 (application/json)

    + Headers
            
            Location: /prediccion/Id            
    + Body
            
             {
                "result": True,
                "message": "prediccion no encontrada"
                }
                
+ Response 200 (application/json)
     
    + Headers
            
            Location: /prediccion/Id
     
     
    + Body
            
             {
                "result": True,
                "message": "prediccion eliminada"
                }



## GrabarCD [/grabacd]
+ Attributes
 + Id (number, required) - Identity
 + Descripcion (string)
 + Desde (string)
 + Cam (string)
 + Direccion (string)
 + Lat (string)
 + Lon (string)

### Grabacd [GET]


+ Response 200 (application/json)


        {
            "Id":1,
            "descripcion": "Descripción video tiempo real",
            "desde": "http://video/grabacion/1/",
            "cam":{
                    "Direccion":"Teatinos 280",
                    "Lat":"-33.44317211114969",
                    "Lon":"-70.65781510449221"
            }
        }



## AttImpresion [/AttImpresion]
+ Attributes
 + Id (number, required) - Identity
 + color (string)
 + tamano (string)
 + tipoletra (enum[string])
    +Arial
    +Comic sans
    +Calibri
    +Times new roman
 + fuente (enum[number])
    +8
    +10
    +12
    +14
    +16
    +18

 
### AttImpresion [GET]

+ Response 200 (application/json)

        [
                {
                  "AttImpresion": {
                    "Id":1,
                    "color": "Azul",
                    "tamano": "Regular",
                    "tipoletra": "Calibri",
                    "fuente": 14
                  }
                }
                    ]
+ Response 404 (application/json)
    + Headers

            Location: /AttImpresion/Id
    
    + Body
            
                {
                "result": True,
                "message": "No encontrado(a)"
                }        
### Crea AttImpresion [POST]


+ Request (application/json)

        [
                {
                 "AttImpresion": {
                    "Id":2,
                    "color": "Negro",
                    "tamano": "Regular",
                    "tipoletra": "Calibri",
                    "fuente": 16
                  }
                }
        ]

+ Response 201 (application/json)

    + Headers

            Location: /AttImpresion/color/Negro/tamano/Regular/tipoletra/Calibri/fuente/16

    + Body

                {
                 "AttImpresion": {
                    "Id":2,
                    "color": "Negro",
                    "tamano": "Regular",
                    "tipoletra": "Calibri",
                    "fuente": 16
                  }
                }
                
+ Response 404 (application/json)
    + Headers

            Location: /AttImpresion/Id

    + Body
                
                
                {
                "result": True,
                "message": "No encontrado(a)"
                }
                
+ Response 409 (application/json)
    + Headers

            Location: /AttImpresion/Id
            
    + Body
                
                
                {
                "result": True,
                "message": "El recurso ya existe."
                }
### Actualiza AttImpresion [PUT]
+ Request (application/json)

        {
                 "AttImpresion": {
                    "Id":2,
                    "color": "Negro",
                    "tamano": "Regular",
                    "tipoletra": "Calibri",
                    "fuente": 16
                  }
        }

+ Response 204 (application/json)

    + Headers
            
            Location: /AttImpresion/color/Negro/tamano/Regular/tipoletra/Calibri/fuente/16
            

+ Response 400 (application/json)

    + Headers
    
            Location: /AttImpresion/Id
    
    + Body
    
              {
                 "result": True,
                 "message": "no encontrada"
              }

+ Response 404 (application/json)

    + Headers   
    
            Location: /AttImpresion/Id
    
    + Body
    
              {
                 "result": True,
                 "message": "no disponible"
              }                                
### Elimina AttImpresion [DELETE]
+ Response 404 (application/json)

    + Headers
            
            Location: /AttImpresion/Id            
    + Body
            
             {
                "result": True,
                "message": "AttImpresion no encontrada"
                }
                
+ Response 200 (application/json)
     
    + Headers
            
            Location: /AttImpresion/Id
     
     
    + Body
            
             {
                "result": True,
                "message": "AttImpresion eliminada"
                }
                
## Mapa [/Mapa]
+ Attributes
 + Id (string, required) - Identity
 + Ubicacion (string)
 + Lat (object, required)
 + Lon (object, required)









### Mapa [GET]

+ Response 200 (application/json)

        [
            {
              "Mapa": {
                "Id":1,
                "Ubicacion": "Alameda Gral.Bernardo O´Higgins ",
                "Lat": "-33.44317211114969",
                "Lon": "-70.65781510449221"
              }
            }
         ]
+ Response 404 (application/json)
    + Headers

            Location: /mapa/Id
    
    + Body
            
                {
                "result": True,
                "message": "No encontrado(a)"
                }            
### Crea Mapa [POST]


+ Request (application/json)

        [
                {
              "Mapa": {
                "Id":1,
                "Ubicacion": "Alameda Gral.Bernardo O´Higgins ",
                "Lat": "-63.00101",
                "Lon": "-62.1122"
              }
                }
        ]

+ Response 201 (application/json)

    + Headers

            Location: /mapa/Id/Ubicacion/Teatinos 300/Lat/-62.20101/Lon/-62.12342

    + Body

                {
              "Mapa": {
                "Id":2,
                "Ubicacion": "Teatinos 300",
                "Lat": "-62.20101",
                "Lon": "-62.12342"
              }
                }   
+ Response 404 (application/json)
    + Headers

            Location: /mapa/Id

    + Body
                
                
                {
                "result": True,
                "message": "No encontrado(a)"
                }
                
+ Response 409 (application/json)
    + Headers

            Location: /mapa/Id
            
    + Body
                
                
                {
                "result": True,
                "message": "El recurso ya existe."
                }
### Actualiza Mapa [PUT]
+ Request (application/json)

        {
              "Mapa": {
                "Id":2,
                "Ubicacion": "Alameda Gral.Bernardo O´Higgins ",
                "Lat": "-63.00101",
                "Lon": "-62.1122"
              }
        }

+ Response 204 (application/json)

    + Headers
            
               Location: /mapa/Id/Ubicacion/Alameda Gral.Bernardo O´Higgins/Lat/-63.00101/Lon/-62.1122


+ Response 400 (application/json)

    + Headers        
    
    
    + Body
    
              {
                 "result": True,
                 "message": "no encontrada"
              }

+ Response 404 (application/json)

    + Headers   
    
    + Body
    
              {
                 "result": True,
                 "message": "no disponible"
              }                                                
### Elimina Mapa [DELETE]
+ Response 404 (application/json)

    + Headers
            
            Location: /mapa/Id                    
    + Body
            
             {
                "result": True,
                "message": "mapa no encontrado"
                }
                
+ Response 200 (application/json)
     
    + Headers
            
            Location: /mapa/Id
     
     
    + Body
            
             {
                "result": True,
                "message": "mapa eliminado"
                }


## Texto [/texto]
+ Attributes
 + Id (string, required) - Identity
 + AmbitoO (string, required) - Obligatorio
 + NumeroBloques (number, required) - Obligatorio
 + AttSobreImpresion (string, required) - Obligatorio
 + Tamano (number , required) - Obligatorio
 + TipoCatarter (number, required) - Obligatorio
 

### Texto [GET]

+ Response 200 (application/json)

        [
                {
                  "Texto": {
                    "Id":1,
                    "AmbitoO": "Alto ",
                    "NumeroBloques": 3,
                    "AttSobreImpresion": "Ancho",
                    "Tamano": 10,
                    "TipoCatarter": 9
                  }
                }
         ]
+ Response 404 (application/json)
    + Headers

            Location: /texto/Id
    
    + Body
            
                {
                "result": True,
                "message": "No encontrado(a)"
                }            
### Crea Texto [POST]


+ Request (application/json)

        [
                {
                  "Texto": {
                    "Id":2,
                    "AmbitoO": "Alto ",
                    "NumeroBloques": 3,
                    "AttSobreImpresion": "Ancho",
                    "Tamano": 10,
                    "TipoCatarter": 9
                  }
                }
        ]

+ Response 201 (application/json)

    + Headers

            Location: /texto/1/AmbitoO/Alto/NumeroBloques/6/AttSobreImpresion/Ancho/Tamano/11/TipoCatarter/19

    + Body

                    {
                  "Texto": {
                    "Id":2,
                    "AmbitoO": "Alto",
                    "NumeroBloques": 6,
                    "AttSobreImpresion": "Ancho",
                    "Tamano": 11,
                    "TipoCatarter": 19
                  }
                }   
+ Response 404 (application/json)
    + Headers

            Location: /texto/Id

    + Body
                
                
                {
                "result": True,
                "message": "No encontrado(a)"
                }
                
+ Response 409 (application/json)
    + Headers

            Location: /texto/Id
            
    + Body
                
                
                {
                "result": True,
                "message": "El recurso ya existe."
                }
### Actualiza Texto [PUT]
+ Request (application/json)

        {
                  "Texto": {
                    "Id":,
                    "AmbitoO": "Alto",
                    "NumeroBloques": 3,
                    "AttSobreImpresion": "Ancho",
                    "Tamano": 10,
                    "TipoCatarter": 9
                  }
        }

+ Response 204 (application/json)

    + Headers
            
            Location: /texto/1/AmbitoO/Alto/NumeroBloques/3/AttSobreImpresion/Ancho/Tamano/10/TipoCatarter/9
            

+ Response 400 (application/json)

    + Headers        
    
    
    + Body
    
              {
                 "result": True,
                 "message": "no encontrada"
              }

+ Response 404 (application/json)

    + Headers   
    
    + Body
    
              {
                 "result": True,
                 "message": "no disponible"
              }                                                                
### Elimina Texto [DELETE]
+ Response 404 (application/json)

    + Headers
            
            Location: /texto/Id                    
    + Body
            
             {
                "result": True,
                "message": "texto no encontrado"
                }
                
+ Response 200 (application/json)
     
    + Headers
            
            Location: /texto/Id
     
     
    + Body
            
             {
                "result": True,
                "message": "texto eliminado"
                }               
                
                
## Grabacion [/grabacion]
+ Attributes
 + Id (string, required) - Identity
 + Periodo (number, required) - Obligatorio
 + Calidad (enum[string])
    +HD - HD
    +Alto -Alta resolucion
    +Medio -Media resolucion
    +Bajo -Baja resolucion
 + Brillo (enum[number])
    +1 - HD
    +2 -Alta resolucion
    +3 -Media resolucion
    +4 -Baja resolucion
 + Color (string)
 + Contraste (enum[number]) 
    +1 - HD
    +2 -Alta resolucion
    +3 -Media resolucion
    +4 -Baja resolucion






### grabacion [GET]

+ Response 200 (application/json)

          [
             {
              "Grabacion": {
                "Id":1,
                "Periodo": "20",
                "Calidad": "HD",
                "Brillo": "Alta resolucion",
                "Color": "Azul",
                "Contraste": "Media resolucion"
              }
            }
         ]
+ Response 404 (application/json)
    + Headers

            Location: /grabacion/Id
    
    + Body
            
                {
                "result": True,
                "message": "No encontrado(a)"
                }            
### Crea grabacion [POST]


+ Request (application/json)

           [
                 {
               "Grabacion": {
                "Id":2,
                "Periodo": "30",
                "Calidad": "HD",
                "Brillo": "Alta resolucion",
                "Color": "Verde",
                "Contraste": "Media resolucion"
              }
                }
          ]
          
          

+ Response 201 (application/json)



    + Headers

            Location: /grabacion/Periodo/30/Calidad/HD/Brillo/Alta resolucion/Color/Verde/Contraste/Media resolucion



    + Body
    
               {
               "Grabacion": {
                "Id":2,
                "Periodo": "30",
                "Calidad": "HD",
                "Brillo": "Alta resolucion",
                "Color": "Verde",
                "Contraste": "Media resolucion"
              }
                }  
+ Response 404 (application/json)
    + Headers

            Location: /grabacion/Id

    + Body
                
                
                {
                "result": True,
                "message": "No encontrado(a)"
                }
                
+ Response 409 (application/json)
    + Headers

            Location: /grabacion/Id
            
    + Body
                
                
                {
                "result": True,
                "message": "El recurso ya existe."
                }
### Actualiza grabacion [PUT]
+ Request (application/json)

        {
               "Grabacion": {
                "Id":2,
                "Periodo": "30",
                "Calidad": "HD",
                "Brillo": "Alta resolucion",
                "Color": "Verde",
                "Contraste": "Media resolucion"
              }
        }

+ Response 204 (application/json)

    + Headers
            
            Location: /grabacion/Periodo/30/Calidad/HD/Brillo/Alta resolucion/Color/Verde/Contraste/Media resolucion
            

+ Response 400 (application/json)

    + Headers        
    
    
    + Body
    
              {
                 "result": True,
                 "message": "no encontrada"
              }

+ Response 404 (application/json)

    + Headers   
    
    + Body
    
              {
                 "result": True,
                 "message": "no disponible"
              }                                                                                
### Elimina usuario [DELETE]
+ Response 404 (application/json)

    + Headers
            
            Location: /grabacion/Id                    
    + Body
            
             {
                "result": True,
                "message": "grabacion no encontrada"
                }
                
+ Response 200 (application/json)
     
    + Headers
            
            Location: /grabacion/Id
     
     
    + Body
            
             {
                "result": True,
                "message": "grabacion eliminada"
                }                                
