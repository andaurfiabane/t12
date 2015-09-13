FORMAT: 1A
HOST: http://polls.apiblueprint.org/

# Tarea 10 - Control de tr�fico urbano

Esta es una simple API de consulta de videos on-line y grabaciones.


## Videos [/videos]

### Listado de videos [GET /videos]

Permite obtener una lista de los videos grabados.
 
+ Response 200 (application/json)

    + Body

             [
                {
                "Videos": [
                    {
                            "Video": {
                            "id": 1,
                            "inicioTransmisi�n": "12:02:00",
                            "finTransmisi�n": "12:04:30",
                            "fechaGrabaci�n": "2015-08-01",
                            "horaGrabaci�n": "12:04:35",
                            "formatoCompresi�n": "XviD",
                            "formato": "AVI",
                            "factorCalidad": "Alta",
                            "brillo": 10,
                            "color": "rgba(0,0,0)",
                            "contraste": 20,
                            "urlDescarga": "http://www.ejemplovideo.com/videos/?video=1",
                            "idCamara": "Cam_03"
                                     }
                    },
                     {
                            "Video": {
                            "id": 2,
                            "inicioTransmisi�n": "14:52:00",
                            "finTransmisi�n": "14:56:55",
                            "fechaGrabaci�n": "2015-08-24",
                            "horaGrabaci�n": "14:57:02",
                            "formatoCompresi�n": "XviD",
                            "formato": "AVI",
                            "factorCalidad": "Alta",
                            "brillo": 25,
                            "color": "rgba(0,0,0)",
                            "contraste": 25,
                            "urlDescarga": "http://www.ejemplovideo.com/videos/?video=2",
                            "idCamara": "Cam_01"
                                     }
                    },
                     {
                            "Video": {
                            "id": 3,
                            "inicioTransmisi�n": "10:00:00",
                            "finTransmisi�n": "10:05:00",
                            "fechaGrabaci�n": "2015-08-29",
                            "horaGrabaci�n": "10:05:06",
                            "formatoCompresi�n": "XviD",
                            "formato": "AVI",
                            "factorCalidad": "Alta",
                            "brillo": 10,
                            "color": "rgba(0,0,0)",
                            "contraste": 10,
                            "urlDescarga": "http://www.ejemplovideo.com/videos/?video=3",
                            "idCamara": "Cam_02"
                                     }
                    },
                     {
                            "Video": {
                            "id": 4,
                            "inicioTransmisi�n": "12:52:00",
                            "finTransmisi�n": "12:59:55",
                            "fechaGrabaci�n": "2015-09-05",
                            "horaGrabaci�n": "13:00:00",
                            "formatoCompresi�n": "XviD",
                            "formato": "AVI",
                            "factorCalidad": "Alta",
                            "brillo": 15,
                            "color": "rgba(0,0,0)",
                            "contraste": 25,
                            "urlDescarga": "http://www.ejemplovideo.com/videos/?video=4",
                            "idCamara": "Cam_01"
                                     }
                    }
                          ]
                 }
             ] 

### B�squeda de videos [GET /videos/busqueda?fechaGrabacion=fechaGrabacion&sort=-id]

Permite la b�squeda de videos grabados.
 
+ Response 200 (application/json)

    + Body

             [
                {
                "Videos": [
                    {
                            "Video": {
                            "id": 8,
                            "inicioTransmisi�n": "12:02:00",
                            "finTransmisi�n": "12:04:30",
                            "fechaGrabaci�n": "2015-08-01",
                            "horaGrabaci�n": "12:04:35",
                            "formatoCompresi�n": "XviD",
                            "formato": "AVI",
                            "factorCalidad": "Alta",
                            "brillo": 10,
                            "color": "rgba(0,0,0)",
                            "contraste": 20,
                            "urlDescarga": "http://www.ejemplovideo.com/videos/?video=1",
                            "idCamara": "Cam_03"
                                     }
                    },
                     {
                            "Video": {
                            "id": 7,
                            "inicioTransmisi�n": "14:52:00",
                            "finTransmisi�n": "14:56:55",
                            "fechaGrabaci�n": "2015-08-01",
                            "horaGrabaci�n": "14:57:02",
                            "formatoCompresi�n": "XviD",
                            "formato": "AVI",
                            "factorCalidad": "Alta",
                            "brillo": 25,
                            "color": "rgba(0,0,0)",
                            "contraste": 25,
                            "urlDescarga": "http://www.ejemplovideo.com/videos/?video=2",
                            "idCamara": "Cam_01"
                                     }
                    }
                          ]
                 }
             ] 


### Reproducci�n de video [GET /videos/{id}/reproduccion/]

Permite la reproducci�n de grabaciones de video.

+ Request (application/json)
  
+ Parameters
  + id (required, int)

+ Response 200 (application/json)

    + Body

            {
                "Reproducci�n": 
                    {
                      "Video": {
                        "id": 5,
                        "factorCalidad": "Alta",
                        "brillo": 18,
                        "color": "rgba(0,0,0)",
                        "contraste": 22,
                        "idCamara": "Cam_02",
                        "duraci�nVideo": 180,
                        "formatoDuraci�n": "Segundos"
                             }       
                    }
                               
             }

### Captura de im�genes de video [GET /videos/{id}/?capturas=1]

Permite obtener una determinada cantidad de im�genes de un video grabado.
 
+ Response 200 (application/json)

    + Body

             [
                {
                "Imagenes": [
                    {
                            "Imagen": {
                            "id": 12,
                            "formato": "PNG",
                            "Resoluci�n": "1024x768"
                                     }
                    }
                            ]
                }
             ] 


## C�maras [/camaras]

 
### Listado de c�maras [GET /camaras]

Permite listar las c�maras disponibles.
 
+ Response 200 (application/json)

    + Body

             [
                {
                "Camaras": [
                    {
                            "camara": {
                            "id": "Cam_01",
                            "factorCalidad": "Alta",
                            "brillo": 10,
                            "color": "rgba(0,0,0)",
                            "contraste": 20,
                            "ip": "192.168.1.22",
                            "ubicacion": "Agustinas 288922"
                                     }
                    },
                     {
                            "camara": {
                            "id": "Cam_02",
                            "factorCalidad": "Alta",
                            "brillo": 42,
                            "color": "rgba(0,0,0)",
                            "contraste": 10,
                            "ip": "192.168.1.23",
                            "ubicacion": "Ahumada 224466"
                                     }
                    }
                          ]
                 }
             ] 

### Cambiar calidad de transmisi�n [PUT /camaras/{?id}]

Permite modificar la calidad de transmisi�n de una c�mara.

+ Request (application/json)
  

    + Body
    
            {
                 "Transmisi�n_on-line": {
                            "factorCalidad": "Alta",
                            "brillo": 10,
                            "color": "rgba(0,0,0)",
                            "contraste": 13
                            }
            }

+ Response 201 (application/json)

    + Body

            {
                "Mensaje": "Calidad de transmisi�n modificada correctamente!"
            }            

### B�squeda de c�maras cercanas [GET /camaras/busqueda/{?ubicacion}]

Permite listar las c�maras cercanas a una ubicaci�n.
 
+ Request (application/json)
  
+ Parameters
  + ubicacion (required, string)

+ Response 200 (application/json)

    + Body

             [
                {
                "Camaras": [
                    {
                            "camara": {
                            "id": "Cam_01",
                            "factorCalidad": "Alta",
                            "brillo": 10,
                            "color": "rgba(0,0,0)",
                            "contraste": 20,
                            "ip": "192.168.1.22",
                            "ubicacion": "Ahumada 224466"
                                     }
                    }
                          ]
                 }
             ] 


## Transmisiones [/transmisiones]     

### Listado de transmisiones de video [GET /transmisiones]

Listado de transmisiones de video en l�nea.

+ Response 200 (application/json)

     + Body
    
              {
                 "Transmisiones": [
                          {
                              "Transmisi�n_on-line": {
                              "id": 8,
                              "urlTransmision": "http://www.ejemplotransmision.com/transmision/?idCamara=Cam_01&idTransmision=8",
                              "factorCalidad": "Alta",
                              "brillo": 18,
                              "color": "rgba(0,0,0)",
                              "contraste": 22,
                              "inicioTransmisi�n": "11:55:40",
                              "idCamara": "Cam_01"
                                                     }
                           },
                           {
                              "Transmisi�n_on-line": {
                              "id": 9,
                              "urlTransmision": "http://www.ejemplotransmision.com/transmision/?idCamara=Cam_02&idTransmision=9",
                              "factorCalidad": "Alta",
                              "brillo": 15,
                              "color": "rgba(0,0,0)",
                              "contraste": 30,
                              "inicioTransmisi�n": "16:55:40",
                              "idCamara": "Cam_02"
                                                     }
                           }
                                   ]
                }

### Transmisi�n de video [GET /transmisiones/{?id}]

Permite la transmisi�n de video on-line.

+ Request (application/json)
  
+ Parameters
  + id (required, int)
  
 
+ Response 200 (application/json)

    + Body
    
            {
                "Transmisi�n_on-line": 
                    {
                      "id": 5,
                      "urlTransmision": "http://www.ejemplotransmision.com/transmision/?idCamara=Cam_02&idTransmision=8",
                      "factorCalidad": "Alta",
                      "brillo": 18,
                      "color": "rgba(0,0,0)",
                      "contraste": 22,
                      "inicioTransmisi�n": "11:55:40",
                      "idCamara": "Cam_02"
                    }
                               
             }
  
  
### Captura de im�genes de transmisiones en l�nea [GET /transmisiones/{id}/?capturas=2]

Permite obtener una determinada cantidad de im�genes de una transmisi�n en l�nea.
 
+ Response 200 (application/json)

    + Body

             [
                {
                "Imagenes": [
                    {
                            "Imagen": {
                            "id": 1,
                            "formato": "PNG",
                            "Resoluci�n": "1024x768"
                                     }
                    },
                     {
                            "Imagen": {
                            "id": 2,
                            "formato": "PNG",
                            "Resoluci�n": "1024x768"
                                     }
                    }
                          ]
                 }
             ] 
  
             


   